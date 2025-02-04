Snowflake
=========

In Fire Insights, Connections can be made to Snowflake. This can be used in the Snowflake nodes in the Workflow Editor for reading and writing data to Snowflake.


Creating Connection
-------------------
Create a connection in Fire Insights for Snowflake.

It can be created by the Administrator under Administration/Global Connections. These connections are available for everyone to use.

It can also be created by any user with their Application. In this case, it is only available to the Application and its users.

Specify your Snowflake Username, Password and Url and save the details.

.. figure:: ../../_assets/connections/snowflake-add-con.PNG 
   :alt: snowflake
   :width: 40%

We can also test the specified connection before saving the connection details. 

Now we are ready to start using the Snowflake Connection in Fire Insights.


Read Snowflake Node
-------------------
Fire now enables you to read data from snowflake using this node.

List of all created snowflake connection will be listed and user can choose any one to read data.

Add all required details eg. SF DATABASE, SF SCHEMA, SF WAREHOUSE, SF TABLE. 

Refresh schema before continuing further.

.. figure:: ../../_assets/connections/read_snowflake_node.PNG
   :alt: snowflake
   :width: 40%

Write Snowflake Node
--------------------
Fire now enables you to write data to snowflake using this node.

List of all created snowflake connection will be listed and user can choose any one to read data.

Add all required details eg. SF DATABASE, SF SCHEMA, SF WAREHOUSE, SF TABLE. 

For eg. Can read data from csv and write to snowflake.

.. figure:: ../../_assets/connections/write_to_snowflake_node.PNG
   :alt: snowflake
   :width: 40%
