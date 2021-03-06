---
title: "Azure Data Lake Analytics Connection Manager | Microsoft Docs"
ms.custom: ""
ms.date: "05/18/2018"
ms.prod: sql
ms.prod_service: "integration-services"
ms.component: "connection-manager"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: conceptual
f1_keywords: 
  - "SQL13.DTS.DESIGNER.AFPADLSCM.F1"
  - "sql14.dts.designer.afpadlscm.f1"
ms.assetid: f4c44553-0f08-4731-ac47-7534990b8c8d
caps.latest.revision: 7
author: "yanancai"
ms.author: "yanacai"
ms.reviewer: "douglasl"
manager: craigg
---

# Azure Data Lake Analytics Connection Manager

A SQL Server Integration Services (SSIS) package can use the Azure Data Lake Analytics connection manager to connect to an Azure Data Lake Analytics account with one of the two following authentication types:
-   Azure AD User Identity
-   Azure AD Service Identity 

The Azure Data Lake Analytics connection manager is a component of the [SQL Server Integration Services (SSIS) Feature Pack for Azure](../../integration-services/azure-feature-pack-for-integration-services-ssis.md).
 
## Configure the Azure Data Lake Analytics Connection Manager

1.  In the **Add SSIS Connection Manager** dialog box, select **AzureDataLakeAnalytics**, and then select **Add**. The **Azure Data Lake Analytics Connection Manager Editor** dialog box opens.
  
2.  In the **Azure Data Lake Analytics Connection Manager Editor** dialog box, in the **ADLA Account Name** field, provide the Azure Data Lake Analytics account name. For example: myadlaaccountname.
  
3.  In the **Authentication** field, choose the appropriate authentication type to access the data in Azure Data Lake Analytics.

    1.  If you select the **Azure AD User Identity** authentication option, do the following things:
        1. Provide values for the **User Name** and **Password** fields. 
    
        2. To test the connection, select **Test Connection**. If you or the tenant administrator didn't previously consent to allow SSIS to access your Azure Data Lake Analytics account, select **Accept** when prompted. For more information about this consent experience, see [Integrating applications with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-integrating-applications#updating-an-application).
    
        >   [!NOTE] 
        > When you select the **Azure AD User Identity** authentication option, multi-factor authentication and Microsoft account authentication are not supported.
    
    2. If you select the **Azure AD Service Identity** authentication option, do the following things:
        1. Create an Azure Active Directory (AAD) application and service principal to access the Azure Data Lake Analytics account. For more information about this authentication option, see [Use portal to create Active Directory application and service principal that can access resources](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal).
    
        2. Assign appropriate permissions to let this AAD application accesses your Azure Data Lake Analytics account. Learn how to grant permissions to your Azure Data Lake Analytics account [using Add User Wizard](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-manage-use-portal#add-a-new-user). 
    
        3. Provide values for the **Application ID**, **Authentication Key**, and **Tenant ID** fields.
    
        4. To test the connection, select **Test Connection**.  

4.  Select **OK** to close the **Azure Data Lake Analytics Connection Manager Editor** dialog box.  

## View the properties of the connection manager
You can see the properties of the connection manager you created in the **Properties** window.  
  
  
