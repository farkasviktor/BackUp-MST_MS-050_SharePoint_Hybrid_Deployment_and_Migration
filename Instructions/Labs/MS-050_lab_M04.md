# Module 04- Lab1: Create and Configure Service Applications

## Microsoft 365 user interface 

Given the dynamic nature of Microsoft cloud tools, you may experience user interface (UI) changes that were made following the development of this training content. This will manifest itself in UI changes that do not match up with the detailed instructions presented in this lab manual.

The Microsoft World-Wide Learning team will update this training course as soon as any such changes are brought to our attention. However, given the dynamic nature of cloud updates, you may run into UI changes before this training content is updated. **If this occurs, you will have to adapt to the changes and work through them in the lab exercises as needed.**

## Lab Scenario 

In the labs of this course you are the Administrator for Adatum Corporation, and you have to setup services

  - Create BCS (Business Connectivity Services) Service Application

  - Create Secure Store Service Application

  - Create MMS (Managed Metadata Services) Service Application

  - Create App Management Service Application

In this lab, you will create and configure the following service applications in SharePoint 2019.

- **Exercise 1: Create a Business Connectivity Service Application (5 minutes)**

    - Task 1: Create an application pool account

    - Task 2: Register a service accounts as SharePoint managed account

    - Task 3: Create a BCS Service Application

- **Exercise 2: Create a Secure Store Service Application (5 minutes)**

  - Task 1: Create a Secure Store Service Application

- **Exercise 3: Create a Managed Metadata Service Application (5 minutes)**


  - Task 1: Register a service account as SharePoint managed account

  - Task 2: Create a Managed Metadata Service Application

- **Exercise 4: Create an App Management Service Application (5 minutes)**

  - Task 1: Create an App Management Service Application

## Objectives

After you complete this lab, you will be able to:

  - Create a Business Connectivity Service Application

  - Create a Secure Store Service Application

  - Create a Managed Metadata Service Application

  - Create an App Management Service Application

## Lab Setup 

  - **Estimated Time:** 20 minutes.

## Instructions

## Before you start

### Review the lab virtual machines

The following are the virtual machines provided in this course. You will log in to the VM as a local administrator. The instructor will provide the sign-in information.

  - LON-DC1: Domain controller

  - LON-SP1: SharePoint Server with SharePoint 2019 installed.

  - LON-SP2: SharePoint Server with SharePoint 2019 installed.

  - LON-SQL: SQL Server with SQL Server management tools installed.

## Exercise 1: Create and Configure Business Connectivity Service Application

In the first exercise you will walk through the steps to create and configure the BCS service application.

### Task 1 – Create an application pool account

1.  Sign in to **LON-DC1** virtual machine as the Administrator (Adatum\\administrator).

2.  Go to **Start** \> **Windows Administrative Tools** \> **Active Directory Administrative Center.**

3.  In Active Directory Administrative Center, select **Adatum(local)**.

4.  In the **Adatum**(local) pane, right select on the **IT** OU, select **New\>User**.

5.  In the **Create User** dialog box, fill out the properties, and hit **OK.**

    - Full name: Application Pool

    - User UPN logon: SPAppPool

    - Password: Pa55w.rd

    - Confirm password: Pa55w.rd

    - Click Other password options, select Password never expires, select User cannot change password.


6.  Select **OK**.

### Task 2 – Register Service Accounts as SharePoint Managed Accounts

1.  Log on to **LON-SP1** virtual machine as the SharePoint Farm Administrator (Adatum\\SPFarm).

2.  On the **Start** menu, expand **Microsoft SharePoint 2019 Products**, select **SharePoint 2019 Central Administration**.

3.  In Central Administration, select **Security**, then on the Security page, under **General Security**, select **Configure Managed Accounts**.

4.  On the **Managed Accounts** page, select **Register Managed Account**.

5.  Create a new managed account by entering the following information under **Service Account Credentials**, then select **OK**.
    
    - Username: **adatum\\SPAppPool**

    - Password: **Pa55w.rd**

### Task 3 – Create BCS Service Application 

In this task you will create the BCS service application.

1.  Log on to **LON-SP1** virtual machine as the SharePoint Farm Administrator (Adatum\\SPFarm).

2.  On the **Start** menu, expand **Microsoft SharePoint 2019 Products**, select **SharePoint 2019 Central Administration**.

3.  In Central Administration, select **Application Management**, then on the Application Management page, under the **Service Applications** section, select **Manage Service Applications**.

4.  On the **Manage Service Applications** page, select **New** from the ribbon and select **Business Data Connectivity Service**.

5.  Use the following information to create the BCS Service Application
    
    - Service Application Name: **BCS**

    - Database Name: **BCS\_Service\_DB**

    - Create new application pool – Application Pool Name: **SPServicesAppPool**

    - Create new application pool – Security Account: **ADATUM\\SPAppPool**

    - Select **OK**.

6.  Select **OK** on the creation summary page.

You have now completed this task and the exercise. You can proceed to the next Exercise.

## Exercise 2: Create and Configure Secure Store Service Application

In this exercise you will create and configure the secure store service application.

### Task 1 – Create Secure Store Service Application 

In this task you will create the Secure Store service application.

1.  Log on to **LON-SP1** virtual machine as the SharePoint Farm Administrator (Adatum\\SPFarm).

2.  On the **Start** menu, expand **Microsoft SharePoint 2019 Products**, select **SharePoint 2019 Central Administration**.

3.  In Central Administration, select **Application Management**, then on the Application Management page, under the **Service Applications** section, select **Manage Service Applications**.

4.  On the **Manage Service Applications** page, select **New** from the ribbon and select **Secure Store Service**.

5.  Use the following information to create the Managed Metadata Service Application
    
    - Name: **Secure Store**

    - Database Name: **Secure\_Store\_Service\_DB**

    - Use Existing Application Pool: **SPServicesAppPool**

    - Select **OK**.

## Exercise 3: Create and Configure Managed Metadata Service Application

In this exercise you will create and configure the managed metadata service application.

### Task 1 – Register Service Accounts as SharePoint Managed Accounts 

1.  Log on to **LON-SP1** virtual machine as the SharePoint Farm Administrator (Adatum\\SPFarm).

2.  On the **Start** menu, expand **Microsoft SharePoint 2019 Products**, select **SharePoint 2019 Central Administration**.

3.  In Central Administration, select **Security**, then on the Security page, under **General Security**, select **Configure Managed Accounts**.

4.  On the **Managed Accounts** page, click on **Register Managed Account**.

5.  Create a new managed account by entering the following information under **Service Account Credentials**, then click **OK**.
    
    - Username: **adatum\\spMMS**

    - Password: **Pa55w.rd**

### Task 2 – Create Managed Metadata Service Application 

In this task you will create the Managed Metadata service application.

1.  In Central Administration, select **Application Management**, go to the Application Management page, under the **Service Applications** section, and select **Manage Service Applications**.

2.  On the **Manage Service Applications** page, select **New** from the ribbon and select **Managed Metadata Service**.

3.  Use the following information to create the Managed Metadata Service Application
    
    - Name: **MMS**

    - Database Name: **MMS\_Service\_DB**

    - Create new application pool

    - Application pool name: **MMS**

    - Security account for the application pool: Adatum\\SPMMS

    - Select **OK** (it might take a while for the screen to change).

4.  Once created you can select **MMS** to view the Term Store Administrator interface.

You have now completed this task and the exercise

## Exercise 4: Create and Configure App Management Service Application

In this exercise you will create and configure the App Management service application.

### Task 1 – Create App Management Service Application 

In this task you will create the App Management service application.

1.  Log on to **LON-SP1** virtual machine as the SharePoint Farm Administrator (Adatum\\SPFarm).

2.  On the **Start** menu, expand **Microsoft SharePoint 2019 Products**, select **SharePoint 2019 Central Administration**.

3.  In Central Administration, select **Application Management**, then on the Application Management page, under the **Service Applications** section, select **Manage Service Applications**.

4.  On the **Manage Service Applications** page, select **New** from the ribbon and select **App Management Service**.

5.  Use the following information to create the Managed Metadata Service Application
    
    - Name: **App Management**

    - Database Name: **App\_Management\_Service\_DB**

    - Use Existing Application Pool: **SPServicesAppPool**

    - Select **OK**.

You have now completed this task and the exercise.

END OF LAB



