
.. _Features-RL:Catalyst

Working with RL Catalyst
========================


.. _Import Linux Node and Install latest version of-Tomcat:

Import Linux Node and Install latest version of Tomcat
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. Import Node by IP
 * Click on Import by IP icon in the respective **Environment** of **Workzone**
 * Enter all the details and click on import button

   Please refer to :ref:`import-byip`  for more details

2. Install latest version of Tomcat
 * Click on Chef-Client Run icon on the imported node in Infrastructure -> Instances tab
 * Search for **tomcat-all-rl** cookbook and add to runlist and click on update runlist button

3. To Verify Tomcat is installed access IP address with portnumber 8080



**Following video demonstrates how to import Linux node and install latest version of Tomcat in RLCatalyst:**


.. raw:: html

    
    <div style="position:relative;padding-bottom:56.25%;padding-top:30px;height:0;overflow:hidden;">
        <iframe src="https://www.youtube.com/embed/f5rVD77DZoU" frameborder="0" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
    </div>


*****

.. _Install apache2 on imported node and use service to stop-apache2:

Install apache2 on imported node and use service to stop apache2
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. Creating a Service command
 * In Settings, Under Gallery setup -> Service command, create a new service by selecting service command type as **chef cookbook/recipe**. Search for the **service_apache** in service cookbooks dropdown. Select actions **Start,Stop,Restart** and save.
   
   Please refer :ref:`Service-Command` for more details.


2. Import a Linux Node
 * Click on Import by IP icon in the respective **Environment** of **Workzone**
 * Enter all the details and click on import button

   Please refer to :ref:`import-byip`  for more details.


3. Install Apache using chef client run
 * Click on Chef-Client run button in the Workzone -> Infrastructure -> Instances tab, of the imported node and add **apache2** cookbook and click on Update runlist button

4. Add the service apache to the node
 * Go to Controlpanel -> Service Tab -> Click on Add New Service. Select the service and save.
 

5. Stop the service and check the status
 * Go to Controlpanel -> Services and Click on Stop icon
 * SSH in to the box from catalyst and run **sudo service apache2 status**
   apache2 is running now 


6. Start the service and check the status
 * Go to Controlpanel -> Services and Click on Start icon
 * SSH in to the box from catalyst and run **sudo service apache2 status**
   apache2 is not running


**Following video demonstrates how to Install apache2 on imported node and use service to stop apache2 in RLCatalyst:**


.. raw:: html

    
    <div style="position:relative;padding-bottom:56.25%;padding-top:30px;height:0;overflow:hidden;">
        <iframe src="https://www.youtube.com/embed/f5rVD77DZoU" frameborder="0" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
    </div>


*****


.. _Import Ubuntu Node and Deploy-petclinic:

Import Ubuntu Node and Deploy petclinic
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. Import a Linux Node
 * Click on Import by IP icon in the respective **Environment** of **Workzone**
 * Enter all the details and click on import button

   Please refer to :ref:`import-byip`  for more details.


2. Install Tomcat Cookbook(tomcat-all-rl)
 * Click on Chef-Client Run icon on the imported node in Workzone -> Infrastructure -> Instances tab
 * Search for **tomcat-all-rl** cookbook and add to runlist and click on update runlist button


3. Create a Chef orchestration task, Choose the node and add the cookbook deploy_war) & Edit attributes
  * In Workzone, Under Orchestration Create a New Chef Task and add **deploy_war** cookbook and edit the following attributes
  * Source code url - **https://s3-us-west-2.amazonaws.com/catalystcode/petclinic-2.02.71.war**
  * Application version – 2.02.71
  * Node publice IP – enter the public IP where tomcat is running and present as node in catalyst.

4. Execute the task 
 * After execution of task, access petclinic at <ip>:8080/petclinic



**Following video demonstrates how to Import Ubuntu Node and Deploy petclinic in RLCatalyst:**


.. raw:: html

    
    <div style="position:relative;padding-bottom:56.25%;padding-top:30px;height:0;overflow:hidden;">
        <iframe src="https://www.youtube.com/embed/f5rVD77DZoU" frameborder="0" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
    </div>



*****


.. _Launch New Ubuntu Instance and Install-Jboss:

Launch New Ubuntu Instance and Install Jboss
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. Add Provider
 * In Settings, under DevopsSetup -> Providers, add a New provider by entering the valid details
   
   Please refer to :ref:`provider-settings` for more details.

2. Add VMImage for Ubuntu
 * In Settings, under Gallery setup -> VMImage, add a New VMImage for Ubuntu
   
   Please refer to :ref:`configure-vm` for more details.

3. Create Blueprint using Ubuntu as base Image by adding Jboss Cookbook to runlist
 * In Design, under OSImage template type select ubuntu template and create blueprint by entering the other details and by adding **jboss7_rl** cookbook in configure runlist parameters and save

4. To verify Jboss installtion
 * Launch the Blueprint from Workzone -> Infrastructure -> Blueprints. After launch of Blueprint go to Infrastructure -> Instances, once the node bootstraps verify the Jboss installation at <ip>:8080



**Following video demonstrates how to Launch New Ubuntu Instance and Install Jboss in RLCatalyst:**


.. raw:: html

    
    <div style="position:relative;padding-bottom:56.25%;padding-top:30px;height:0;overflow:hidden;">
        <iframe src="https://www.youtube.com/embed/f5rVD77DZoU" frameborder="0" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
    </div>



*****


.. _Launch Windows Instance and Install-IIS:

Launch Windows Instance and Install IIS
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. Add Provider
 * In Settings, under DevopsSetup -> Providers, add a New provider by entering the valid details

   Please refer to :ref:`provider-settings` for more details.

2. Add VMImage for Windows(Public AMI to be added for Windows2012)
 * In Settings, under Gallery setup -> VMImage, add a New VMImage for Windows

   Please refer to :ref:`configure-vm` for more details.

3. Create Blueprint using Windows base image by adding IIS cookbook to runlist
 * In Design, under OSImage template type select windows template and create blueprint by entering the other details and by adding **iis** cookbook in configure runlist parameters and save

4. Launch Blueprint and Verify IIS Installation
 * Launch the Blueprint from Workzone -> Infrastructure -> Blueprints. After launch of Blueprint go to Infrastructure -> Instances, once the node bootstraps RDP to the machine and in search options search for IIS.Internet Information Services Manager should be available.


**Following video demonstrates how to Launch Windows Instance and Install IIS in RLCatalyst:**


.. raw:: html

    
    <div style="position:relative;padding-bottom:56.25%;padding-top:30px;height:0;overflow:hidden;">
        <iframe src="https://www.youtube.com/embed/f5rVD77DZoU" frameborder="0" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
    </div>


*****


.. _Launch Ubuntu Instance and run Docker container for-Wordpress:

Launch Ubuntu Instance and run Docker container for Wordpress
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. Add Provider
 * In Settings, under DevopsSetup -> Providers, add a New provider by entering the valid details

   Please refer to :ref:`provider-settings` for more details.

2. Add VMImage for Ubuntu
 * In Settings, under Gallery setup -> VMImage, add a New VMImage for Ubuntu

   Please refer to :ref:`configure-vm` for more details.

3. Create a docker template for cadvisor
 * In Gallery setup, under Templates add a New Template by selecting Docker Template type and add docker repo path for cadvisor

4. Create a Docker template for Wordpress
 * In Gallery setup, under Templates add a New Template by selecting Docker Template type and add docker repo path for wordpress

5. Create a blueprint with Ubuntu image and add docker cookbook to runlist
 * In Design, under OSImage template type select ubuntu template and create blueprint by entering the other details and by adding **docker** cookbook in configure runlist parameters and save


6. Create a Blueprint for Docker template using the template cadvisor
  * Add Volume to cadvisor **/:/rootfs:ro,/var/run:/var/run:rw,/sys:/sys:ro,/var/lib/docker/:/var/lib/docker:ro and port 8080:8080**

7. Create a Blueprint for Docker template using the template wordpress
  

8. Launch the blueprint 
 * Launch the Blueprint from Workzone -> Infrastructure -> Blueprints. After Launch of Blueprint go to Infrastructure -> Instances, Wait until the node Bootstrap successfully

9. Launch Cadvisor docker blueprint
 * Go to Workzone -> Infrastructure -> Blueprints -> Docker. Select cadvisor blueprint and select instance in Launch docker bluperint and start.Wait until image pull completes.

10. Launch Wordpress docker blueprint
 * Go to Workzone -> Infrastructure -> Blueprints -> Docker. Select wordpress blueprint and select instance in Launch docker bluperint and start.Wait until image pull completes.

11. Verify the Containers
 * Go to Workzone -> Infrastructure -> Containers and verify 2 containers with name **Cadvisor** and **Wordpress**

12. Check the Health of the Containers
 * Click Graph icon on the respective containers to verify the Health status



**Following video demonstrates how to Launch Ubuntu Instance and run Docker container for Wordpress in RLCatalyst:**


.. raw:: html

    
    <div style="position:relative;padding-bottom:56.25%;padding-top:30px;height:0;overflow:hidden;">
        <iframe src="https://www.youtube.com/embed/f5rVD77DZoU" frameborder="0" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
    </div>



*****

.. _Launch New ubuntu Instance,Install Tomcat,upgrade to-v8.0[attribute]:

Launch New ubuntu Instance,Install Tomcat,upgrade to v8.0[attribute]
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. Add Provider
 * In Settings, under DevopsSetup -> Providers, add a New provider by entering the valid details

   Please refer to :ref:`provider-settings` for more details.

2. Add VMImage for Ubuntu
 * In Settings, under Gallery setup -> VMImage, add a New VMImage for Ubuntu

   Please refer to :ref:`configure-vm` for more details.

3. Create Blueprint using Ubuntu as base Image and Tomcat Cookbook
 * In Design, under OSImage template type select ubuntu template and create blueprint by entering the other details and by adding **tomcat-all-rl** cookbook in configure runlist parameters and save

4. Launch Blueprint and Access Tomcat
 * Launch the Blueprint from Workzone -> Infrastructure -> Blueprints. After launch of Blueprint go to Infrastructure -> Instances, once the node bootstraps access Tomcat at <ip>:8080 and check the version

5. Chef Client Run to upgrade Tomcat version to 8.0
 * Click on Chef-Client run button and Edit the cookbook attributes and select the latest version, save and update runlist
   Access Tomcat at <ip>:8080 and check for the version



**Following video demonstrates how to Launch New ubuntu Instance,Install Tomcat,upgrade to v8.0[attribute] in RLCatalyst:**


.. raw:: html

    
    <div style="position:relative;padding-bottom:56.25%;padding-top:30px;height:0;overflow:hidden;">
        <iframe src="https://www.youtube.com/embed/f5rVD77DZoU" frameborder="0" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
    </div>



*****



.. _Launch Java stack using-CFT:

Launch Java stack using CFT
^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. CFT Template
 * In Settings, Under Gallery Setup -> Templates -> create a New CloudFormation template by selecting the **CloudFormation** template type and uploading the valid **Template File** and save

2. Add Provider
 * In Settings, under DevopsSetup -> Providers, add a New provider by entering the valid details

   Please refer to :ref:`provider-settings` for more details.

3. Add VMImage for Ubuntu
 * In Settings, under Gallery setup -> VMImage, add a New VMImage for ubuntu

   Please refer to :ref:`configure-vm` for more details.

4. Create CFT Blueprint using Ubuntu as base Image and by adding Java Cookbook to runlist
 * In Design, under CloudFormation template type select ubuntu template and create CFTblueprint by entering the other details and by adding **Java** cookbook to runlist in configure stack parameters and save

5. Launch CFT Blueprint
 * Launch the Blueprint from Workzone -> Infrastructure -> Blueprints and verify the **Stack** in Infrastructure -> CloudFormation, verify the instance in Infrastructure -> Instances tab



**Following video demonstrates how to Launch Java stack using CFT in RLCatalyst:**


.. raw:: html

    
    <div style="position:relative;padding-bottom:56.25%;padding-top:30px;height:0;overflow:hidden;">
        <iframe src="https://www.youtube.com/embed/f5rVD77DZoU" frameborder="0" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
    </div>



*****


.. _ARM with 2-VirtualMachines[VM]:

ARM with 2 VirtualMachines[VM]
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
1. Add an Azure provider
 * In Settings, under DevopsSetup -> Providers, add a New **Azure** provider by entering the valid details

   Please refer to :ref:`provider-settings` for more details.

2. Create ARM Template
 * In Settings, under Gallery setup -> Templates, create a New ARM template by selecting the **ARMTemplate** template type and uploading the valid **Template File** and save

3. Create Blueprint for ARM Template
 * In Design -> Click on **Azure** provider from tree. Under ARM template type select your ARM template and create ARMBlueprint by entering the other details and save

4. Launch ARMBlueprint
 * Launch the Blueprint from Workzone -> Infrastructure -> Blueprints -> AzureARM and verify the **Deployment** in Infrastructure -> AzureARM, verify the instances in Infrastructure -> Instances tab



**Following video demonstrates how to Create, Launch ARM Blueprint with 2 VirtualMachines[VM] in RLCatalyst:**


.. raw:: html

    
    <div style="position:relative;padding-bottom:56.25%;padding-top:30px;height:0;overflow:hidden;">
        <iframe src="https://www.youtube.com/embed/f5rVD77DZoU" frameborder="0" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
    </div>


*****


.. _Composite-Docker:

Composite Docker
^^^^^^^^^^^^^^^^

1. Add Provider
 * In Settings, under DevopsSetup -> Providers, add a New provider by entering the valid details

   Please refer to :ref:`provider-settings` for more details.

2. Add VMImage for Ubuntu
 * In Settings, under Gallery setup -> VMImage, add a New VMImage for Ubuntu

   Please refer to :ref:`configure-vm` for more details.

3. Create a docker template for cadvisor
 * In Gallery setup, under Templates add a New Template by selecting **Docker** Template type and add **docker repo path for cadvisor**

4. Create a docker template for centos
 * In Gallery setup, under Templates add a New Template by selecting **Docker** Template type and add **docker repo path for centos**


5. Create a Blueprint for Docker and add centos and cadvisor docker templates to a single blueprint (multiple templates to single blueprint)
 * In Design ,select **Docker** template type and select **cadvisor** template and fill the details and click on **Launch parameters** buuton and Add **Volume** to cadvisor **/:/rootfs:ro,/var/run:/var/run:rw,/sys:/sys:ro,/var/lib/docker/:/var/lib/docker:ro** and **port mappings** **8080:8080**. Now click on **Add** and select the **centos** template with **latest** tag and add and save the blueprint

6. Choose the Ubuntu node and run this blueprint. Go to **Containers** tab and verify 2 containers are launched and verify the health by clicking on the Graph icon.


**Following video demonstrates how to do Composite Docker and verify Health in RLCatalyst:**


.. raw:: html

    
    <div style="position:relative;padding-bottom:56.25%;padding-top:30px;height:0;overflow:hidden;">
        <iframe src="https://www.youtube.com/embed/f5rVD77DZoU" frameborder="0" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
    </div>



*****




.. _Provider Sync and-Import Instances:

Provider Sync and Import Instances
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. Add Provider
 * In Settings, under DevopsSetup -> Providers, add a New provider by entering the valid details
   Please refer to :ref:`provider-settings` for more details.

2. Provider Sync
 * Click on Sync instances button of your provider -> **UnManaged Instances** of the created provider

3. Import the instances into Catalyst **[Unmanaged to managed]**
 * Select the Instances and click on Import Instances and enter the valid details and Sync
 * You can see the nodes imported in the respective environments and verify the imported instances is present under **managed instances** tab.


Please refer to :ref:`providersync and-import` for more details.

*****


.. _Update application-version[petclinic]:

Update application version[petclinic]
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. Import a Linux Node
2. Install Tomcat Cookbook(tomcat-all-rl)
3. Create a Chef orchestration task . Choose the node and add the cookbook deploy_war)
4. Execute the task and access petclinic at <ip>:8080/petclinic
5. Edit the task and edit the attribute 'version'
6. Check the petclinic application and verify the version



**Following video demonstrates how to Update application version[petclinic] in RLCatalyst:**


.. raw:: html

    
    <div style="position:relative;padding-bottom:56.25%;padding-top:30px;height:0;overflow:hidden;">
        <iframe src="https://www.youtube.com/embed/f5rVD77DZoU" frameborder="0" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
    </div>


*****


.. _View History of App deployments &-upgrades:

View History of App deployments & upgrades
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. Import node or launch a new node[ubuntu]
2. Install Tomcat Cookbook(tomcat-all-rl)
3. Add cookbook deploy_war and  Edit attributes
  a. Source code url - **https://s3-us-west-2.amazonaws.com/catalystcode/petclinic-2.02.71.war**
  b. Application version – 2.02.71
  c. Node publice ip – enter the public ip where tomcat is running and present as node in catalyst.
4. Once application is installedon on the node .the above cookbook will use app_data_handler cookbook to send the Data to catalyst


**Following video demonstrates how to View History of App deployments & upgrades in RLCatalyst:**


.. raw:: html

    
    <div style="position:relative;padding-bottom:56.25%;padding-top:30px;height:0;overflow:hidden;">
        <iframe src="https://www.youtube.com/embed/f5rVD77DZoU" frameborder="0" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
    </div>



*****


.. _AWS Cost,Usage-Dashboards:

AWS Cost,Usage Dashboards
^^^^^^^^^^^^^^^^^^^^^^^^^
RLCatalyst provides you a consolidated dashboard for tracking your AWS infrastructure cost and usage . This helps you to identify un-used capacity and do better utilization. RLCatalyst summarizes this data for all the AWS provider accounts configured.

Follow the instructions to configure your dashboards:

1. Add Provider
 * In Settings, under DevopsSetup -> Providers, add a New **AWS** provider by entering the valid details

   Please refer to :ref:`provider-settings` for more details.

2. Track -> usage and cost dashboards
 * Click on **Tracks** under provider you will be able to see **Provider Dashboard** and **AWS Summary Dashboard**


**Provider Dashboard**
 This will give you the snapshot of instances - Total Number vs Number of Managed vs Number of Un-Managed.

 .. image:: /images/summary.png


**AWS Summary Dashboard**
 This will give you the snapshot of Total cost, Daily cost etc.

 .. image:: /images/summaryDash.png


**Following video demonstrates how to view AWS Cost,Usage dashboards in RLCatalyst:**


.. raw:: html

    
    <div style="position:relative;padding-bottom:56.25%;padding-top:30px;height:0;overflow:hidden;">
        <iframe src="https://www.youtube.com/embed/N4TiDHC7vzE" frameborder="0" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
    </div>



*****


.. _providersync and-import:

Add Provider and do Provider Sync
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Once the basic data is loaded, you can start exploring RLCatalyst from the Provider-Sync Feature. You can sync nodes from your AWS provider account and convert the nodes to 'Managed' . This will give a control on your AWS infra by letting you track the capacity, cost and usage . Once sync-ed, you can see the summary dashboard from 'Track'


1. **Add your AWS provider** account details in RLCatalyst . Refer to :ref:`provider-settings` for more help
2. **Sync your provider with RLCatalyst**. Once the provider account is added, you can start importing the nodes into RLCatalyst . Importing will bootstrap the nodes with the configured chef server . The imported instances can be managed from the workzone, under the project and environment to which the nodes are imported. Refer to :ref:`provider-sync` for more help



**Following video demonstrates how to add provider and do sync in RLCatalyst:**


.. raw:: html

    
    <div style="position:relative;padding-bottom:56.25%;padding-top:30px;height:0;overflow:hidden;">
        <iframe src="https://www.youtube.com/embed/HIMlbwtc8Zc" frameborder="0" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
    </div>



*****

        


