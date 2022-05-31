## pgsql

### 展示所有表名

```	postgresql
select tablename from pg_tables where schemaname='public' 
```

### 查询表结构

```

select
    col.table_schema,
    col.table_name,
    col.ordinal_position,
    col.column_name,
    col.data_type,
    col.character_maximum_length,
    col.numeric_precision,
    col.numeric_scale,
    col.is_nullable,
    col.column_default,
    des.description
from
    information_schema.columns col left join pg_description des on
    col.table_name::regclass = des.objoid
    and col.ordinal_position = des.objsubid
where
    table_schema = 'public'
    and table_name = 'table_name'
order by ordinal_position;
```



### 建表语句

``` 
-- 建表
CREATE TABLE if not exists public.user
(
  id character varying(32) NOT NULL DEFAULT sys_guid(),
  name character varying(100) NOT NULL,
  gender character varying(50) NOT NULL,
  age character varying(10) NOT NULL,
  id_no character varying(50) NOT NULL,
  created_date timestamp without time zone DEFAULT now(),
  created_by character varying(100) DEFAULT 'system',
  updated_date timestamp without time zone DEFAULT now(),
  update_by character varying(100) DEFAULT 'system',
  CONSTRAINT user_pkey PRIMARY KEY (id)
)with (oids = false);
 
-- 注释
COMMENT ON TABLE public.user IS '用户表';
COMMENT ON COLUMN public.user.id IS '主键';
COMMENT ON COLUMN public.user.name IS '姓名';
COMMENT ON COLUMN public.user.gender IS '性别';
COMMENT ON COLUMN public.user.age IS '年龄';
COMMENT ON COLUMN public.user.id_no IS '身份证号';
COMMENT ON COLUMN public.user.created_date IS '创建时间';
COMMENT ON COLUMN public.user.created_by IS '创建人';
COMMENT ON COLUMN public.user.updated_date IS '更新时间';
COMMENT ON COLUMN public.user.update_by IS '更新人';
 
-- 主键 （如果建表语句里面没添加主键就执行该语句）
alter table public.user
  add constraint user_pkey primary key (id);
 
-- 索引或唯一索引
drop index if exists user_name;
CREATE INDEX user_name ON user (name);
 
drop index if exists user_id_no;
CREATE  UNIQUE INDEX user_id_no ON user (id_no);
 
-- 授权
GRANT ALL ON TABLE public.user TO mydata;
GRANT SELECT, UPDATE, INSERT, DELETE ON TABLE public.user TO mydata_dml;
GRANT SELECT ON TABLE public.user TO mydata_qry;



```







