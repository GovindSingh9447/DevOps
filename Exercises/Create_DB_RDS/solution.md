## Create a MySQL Database with RDS(AWS)

Got to your AWS Console & Search for RDS then Open it.
</br>
<kbd align="center"><img src="Images/1.jpg"/></kbd>
</br>

Now click on Create a Database

Now select the Engine we are using MySQL with version 8.0.30

Templates Should be Free Tier, so it will not charge anything
</br>
<kbd align="center"><img src="Images/2.jpg"/></kbd>
</br>

Give your Database Name & Password (should be 8 characters)

Choose Instance as db.t2.micro 
</br>
<kbd align="center"><img src="Images/3.jpg"/></kbd>
</br>

Storage Allocated as 20 GiB
</br>
<kbd align="center"><img src="Images/4.jpg"/></kbd>
</br>

Enable Storage Autoscaling, we are using 22 Gib as Maximum threshold 
</br>
<kbd align="center"><img src="Images/5.jpg"/></kbd>
</br>

We are also Activating the Backups with 7 Days of Retention 
</br>
<kbd align="center"><img src="Images/6.jpg"/></kbd>
</br>

Let the remaining Settings as it is & Click on Create a Database.

It will Take Some Time to Create a Database, MySQL Database Successfully Created with RDS AWS Service
</br>
<kbd align="center"><img src="Images/7.jpg"/></kbd>
</br>

Follow For More Devops: -

https://www.linkedin.com/in/devops-learning
