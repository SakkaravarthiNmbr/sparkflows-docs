Creating Dataset for AVRO Files
=================

When working with data in Fire Insights, the first step is to create a dataset that you plan to process subsequently. Dataset is a wrapper around your data which makes it easy to handle it in Sparkflows workbench.

When datasets are created, Fire Insights automatically infers the schema using Spark-Avro library.

Datasets
--------

.. figure:: ../../../_assets/tutorials/dataset/1.PNG
   :alt: Dataset
   :width: 60%
   
Dataset Creation
----------------

Navigate to the "Datasets" tab in your application where you want to create a new dataset. Click on the "Create" button and choose "Dataset". In the pop-up choose "AVRO" and then click "OK".   

.. figure:: ../../../_assets/tutorials/dataset/52.PNG
   :alt: Dataset
   :width: 60%
   
Clicking "OK" will take you to Dataset Details page where you can enter information about your dataset. In the screenshot below, we create a dataset from a sample.avro file.   

.. figure:: ../../../_assets/tutorials/dataset/53.PNG
   :alt: Dataset
   :width: 60%

We specified a name, category, description & path of avro file for the dataset we are creating.

Once we have specified the above, we hit the ‘Update Sample data/schema’ button. This brings up the sample data, infers the schema and displays it. We can change the column names and also the data types. Format column is used for specifying the format for date/time fields.

.. figure:: ../../../_assets/tutorials/dataset/54.PNG
   :alt: Dataset
   :width: 60%

.. figure:: ../../../_assets/tutorials/dataset/55.PNG
   :alt: Dataset
   :width: 60%

Clicking the ‘Save’ button saves the new avro dataset. The avro dataset is now ready for use in any workflow within the specific application.

.. figure:: ../../../_assets/tutorials/dataset/56.PNG
   :alt: Dataset
   :width: 60%
   
   
