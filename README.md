# Instructions for Windows
---

## All Downloads
---

1. I went to [here](https://adoptium.net/temurin/archive/?version=17) and downloaded the windows JDK version.

<img width="683" alt="Image" src="https://github.com/user-attachments/assets/a7f34ef4-12ad-4257-94e8-2787d7bc7164" />

After this file downloads, run the file to set up Java (I didn't change any options, I just hit "Next" until it installed). The file path I had after instalation was `C:\Program Files\Eclipse Adoptium\jdk-17.0.14.7-hotspot`. The file being named "Eclipse Adoptium" threw me off. Just be aware of that file name. 

2. [This]() is where I downloaded Spark.

<img width="959" alt="Image" src="https://github.com/user-attachments/assets/138e2218-dacf-4562-b5a6-3a81dae79375" />

3. Next, I followed [Angel Milla's](https://medium.com/@angheljf/installing-apache-spark-on-windows-a923dcc883bc) instructions and downloaded hadoop-3.0.0/bin/winutils.exe file found [here](https://github.com/steveloughran/winutils/blob/master/hadoop-3.0.0/bin/winutils.exe)

<img width="683" alt="Image" src="https://github.com/user-attachments/assets/c35f1c49-6c73-4669-bdf4-6154ed7241c6" />

## Environment Set Up
---

4. After all files are downloaded, You will need to extract the zipped spark file and move the winutils.exe file to the "bin" folder located in the extracted spark file. For example, my file path for the extracted spark file was `C:\spark\spark-3.5.5-bin-hadoop3` and the "bin" folder was one level down, `C:\spark\spark-3.5.5-bin-hadoop3\bin`.

5. Next, I had to set up my all my environment variables. Press `Win + R`, type `sysdm.cpl` to open up the system control panel. Click on the "Advance" tab, click on "Environment Variables", and locate the "Systems Variables" section. You will need to click "New" for each variable in the table.

<img width="683" alt="Image" src="https://github.com/user-attachments/assets/a7f34ef4-12ad-4257-94e8-2787d7bc7164" />

 When you click "New", this will show:
 
<img width="324" alt="Image" src="https://github.com/user-attachments/assets/ddbc6f31-09b1-4178-8e4c-a47ce981f170" />

You'll need to create all of these variables:
| Variable Name              | Variable Value                                         |
| -------------------------- | ------------------------------------------------------ |
| PYSPARK_DRIVER_PYTHON      | jupyter                                                |
| PYSPARK_DRIVER_PYTHON_OPTS | notebook                                               |
| PYSKKPARK_PYTHON           | python                                                 |
| HADOOP_HOME                | C:\spark\spark-3.5.5-bin-hadoop3                       |
| SPARK_HOME                 | C:\spark\spark-3.5.5-bin-hadoop3                       | 
| JAVA_HOME                  | C:\Program Files\Eclipse Adoptium\jdk-17.0.14.7-hotspot| 

**Important:
  - Make sure you click "OK" after you input both the variable name and value to save the variable.
  - Both the `HADOOP_HOME` and `SPARK_HOME` have the same variable value.**

## Final Step: Updating Path
---

6. The final step is updating my path variable. Find your "Path" variable and click "Edit"



Next, click "New" on this pop up:

Then add these three items as new `%JAVA_HOME%\bin`, `%SPARK_HOME%\bin`, and `HADOOP_HOME%\bin`. Click "Ok" until all windows are closed to save changes/updates. 
I was able to run spark after this.
