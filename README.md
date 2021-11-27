# SQL-helper-notes

### rollback, commit, savepoint

```
insert into toys ( toy_id, toy_name, colour ) 
  values ( 8, 'Red Rabbit', 'red' );

commit;

insert into toys ( toy_id, toy_name, colour ) 
  values ( 9, 'Purple Ninja', 'purple' );

exec savepoint third_sp;

insert into toys ( toy_id, toy_name, colour ) 
  values ( 10, 'Blue Dinosaur', 'blue' );

rollback to savepoint third_sp;

select * from toys
where  toy_id in ( 8, 9, 10 );

rollback;

select * from toys
where  toy_id in ( 8, 9, 10 );

```
