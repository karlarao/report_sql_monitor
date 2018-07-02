

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


----------


SQLd360 v1705 (2017-04-14) by Mauro Pagano

SQLd360 is a "free to use" tool to perform an in-depth investigation of a SQL statement. 
It collects detailed information around the SQL. It also helps to document any findings.
SQLd360 installs nothing. For better results execute connected as SYS or DBA.
It takes a few minutes to execute. Output ZIP file can be large (several MBs), so
you may want to execute SQLd360 from a system directory with at least 1 GB of free 
space. 

Steps
~~~~~
1. Unzip SQLd360.zip, navigate to the root sqld360 directory, and connect as SYS, 
   DBA, or any User with Data Dictionary access:

   $ unzip sqld360.zip
   $ cd sqld360
   $ sqlplus dba_user/dba_pwd

2. Execute sqld360.sql indicating two input parameters. The first one is to specify 
   the SQL ID for the SQL you want to analyze. The second one is to specify if your 
   database is licensed for the Oracle Tuning Pack, the Diagnostics Pack or None 
   [ T | D | N ]. Example below specifies SQL ID 0vy6pt4krb3gm, Tuning Pack. 
   Actual days of history used depends on retention period, SQLd360 uses 31 days by default. 
   Edit sql/sqld360_00_config.sql in case a shorter/longer period is desired.

   SQL> @sqld360.sql 0vy6pt4krb3gm T 
   
3. Unzip output sqld360_<dbname>_<sqlid>_<host>_YYYYMMDD_HH24MI.zip into a directory on your PC

4. Review main html file 0001_sqld360_<dbname>_index.html

****************************************************************************************
   
    SQLD360 - Enkitec's Oracle SQL 360-degree View
    Copyright (C) 2015  Mauro Pagano

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <http://www.gnu.org/licenses/>.
