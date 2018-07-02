# report_sql_monitor


You can do a batch run of report generation by inserting the SQL_ID to the plan_table. You can do this by doing manual INSERT or INSERT..SELECT on a filtered list of SQL_IDs. Example below: 
	
	def edb360_secs2go = 3600
	INSERT INTO plan_table (id, statement_id, operation, options, object_node) values (dbms_random.value(1,10000), 'SQLD360_SQLID', '0p1f7w41jj1tq', '111007', NULL);
	INSERT INTO plan_table (id, statement_id, operation, options, object_node) values (dbms_random.value(1,10000), 'SQLD360_SQLID', '3ddvj44c10qqx', '111007', NULL);
	INSERT INTO plan_table (id, statement_id, operation, options, object_node) values (dbms_random.value(1,10000), 'SQLD360_SQLID', '3m8smr0v7v1m6', '111007', NULL);
	INSERT INTO plan_table (id, statement_id, operation, options, object_node) values (dbms_random.value(1,10000), 'SQLD360_SQLID', '3nnj1js6gy2yb', '111007', NULL);
	INSERT INTO plan_table (id, statement_id, operation, options, object_node) values (dbms_random.value(1,10000), 'SQLD360_SQLID', '3sqgkcng6vx8r', '111007', NULL);
	INSERT INTO plan_table (id, statement_id, operation, options, object_node) values (dbms_random.value(1,10000), 'SQLD360_SQLID', '4ky5wgdp7cfg9', '111007', NULL);
	INSERT INTO plan_table (id, statement_id, operation, options, object_node) values (dbms_random.value(1,10000), 'SQLD360_SQLID', '4u5zq7r9y690a', '111007', NULL);
	INSERT INTO plan_table (id, statement_id, operation, options, object_node) values (dbms_random.value(1,10000), 'SQLD360_SQLID', '527pxd1u7r2ms', '111007', NULL);
	INSERT INTO plan_table (id, statement_id, operation, options, object_node) values (dbms_random.value(1,10000), 'SQLD360_SQLID', '5r00xnxnwr6sw', '111007', NULL);
	INSERT INTO plan_table (id, statement_id, operation, options, object_node) values (dbms_random.value(1,10000), 'SQLD360_SQLID', '5r8sf8qp40tj1', '111007', NULL);
	INSERT INTO plan_table (id, statement_id, operation, options, object_node) values (dbms_random.value(1,10000), 'SQLD360_SQLID', '62u6yd5fxykkx', '111007', NULL);
	INSERT INTO plan_table (id, statement_id, operation, options, object_node) values (dbms_random.value(1,10000), 'SQLD360_SQLID', '6q9zvynq8f0h0', '111007', NULL);
	INSERT INTO plan_table (id, statement_id, operation, options, object_node) values (dbms_random.value(1,10000), 'SQLD360_SQLID', '70k1c2rcztmku', '111007', NULL);
	INSERT INTO plan_table (id, statement_id, operation, options, object_node) values (dbms_random.value(1,10000), 'SQLD360_SQLID', '75hqju87zm2tu', '111007', NULL);
	INSERT INTO plan_table (id, statement_id, operation, options, object_node) values (dbms_random.value(1,10000), 'SQLD360_SQLID', '85ku9z8xzqrs8', '111007', NULL);
	INSERT INTO plan_table (id, statement_id, operation, options, object_node) values (dbms_random.value(1,10000), 'SQLD360_SQLID', '86xja0457873s', '111007', NULL);
	INSERT INTO plan_table (id, statement_id, operation, options, object_node) values (dbms_random.value(1,10000), 'SQLD360_SQLID', '9wygvu6cx2npy', '111007', NULL);
	INSERT INTO plan_table (id, statement_id, operation, options, object_node) values (dbms_random.value(1,10000), 'SQLD360_SQLID', '9y6yh5zxs4h7a', '111007', NULL);
	INSERT INTO plan_table (id, statement_id, operation, options, object_node) values (dbms_random.value(1,10000), 'SQLD360_SQLID', 'acc988uzvjmmt', '111007', NULL);
	INSERT INTO plan_table (id, statement_id, operation, options, object_node) values (dbms_random.value(1,10000), 'SQLD360_SQLID', 'anxyyx2tjjz3g', '111007', NULL);
	INSERT INTO plan_table (id, statement_id, operation, options, object_node) values (dbms_random.value(1,10000), 'SQLD360_SQLID', 'cvn54b7yz0s8u', '111007', NULL);
	INSERT INTO plan_table (id, statement_id, operation, options, object_node) values (dbms_random.value(1,10000), 'SQLD360_SQLID', 'czmz1drcftky4', '111007', NULL);
	INSERT INTO plan_table (id, statement_id, operation, options, object_node) values (dbms_random.value(1,10000), 'SQLD360_SQLID', 'dvbv42b3hfyru', '111007', NULL);
	@sqld360.sql 