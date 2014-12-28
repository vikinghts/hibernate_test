HibernateTest
=============

Store and retrieve the SmartMeter data.

Got a lot of my inspiration from this website:
http://crunchify.com/create-very-simple-jersey-rest-service-and-send-json-data-from-java-client/
and here:
http://www.mkyong.com/webservices/jax-rs/jersey-hello-world-example/

For the hibernate part i got inspiration here:
http://www.tutorialspoint.com/hibernate/hibernate_examples.htm

jodatime and hybernate.... Not that easy. Needed to use this:
add to build.gradle    compile 'org.jadira.usertype:usertype.jodatime:2.0.1'
add to *.hbm.xml       <property type="org.jadira.usertype.dateandtime.joda.PersistentDateTime" name="measureDateTime" column="mDateTime"/>

database details:
CREATE DATABASE datamanagerdb
  WITH OWNER =  datamanageruser
       ENCODING = 'UTF8'
       TABLESPACE = pg_default
       CONNECTION LIMIT = -1;
GRANT ALL ON DATABASE datamanagerdb TO datamanageruser;
GRANT CONNECT, TEMPORARY ON DATABASE datamanagerdb TO public;

CREATE ROLE datamanageruser LOGIN
NOSUPERUSER INHERIT NOCREATEDB NOCREATEROLE NOREPLICATION;

alter user datamanageruser with password "bla"

GRANT ALL PRIVILEGES ON DATABASE datamanagerdb to datamanageruser;
GRANT ALL PRIVILEGES ON TABLE MEASUREPOINT to datamanageruser;
GRANT ALL PRIVILEGES ON sequence measurepoint_id_seq  to datamanageruser

to select the database
\c datamanagerdb


