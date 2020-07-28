# User Guide - MO Receipt

<img src="../../../images/banner-mobilefirst-cloudsuite.jpg" alt="banner" style="zoom:100%;" />



# Table of contents

- **[About this guide](#about-this-guide)**
  - [Intended Audience](#intended-audience)
    - [MO Receipt standard functionality](#std-func)
- **[Technical details](#tech-details)**
  - [Get item head details](#item-head)
  - [Get MO List by Facility](#item-by-facility)
  - [Get MO List by Product Number](#item-by-prd)
  - [Submit Report](#report-receipt)

- **[Workflow, Screen Layouts & API Logic](#wrk)**
  - [Settings](#settings)
  - [Item #](#itno)
  - [Select Order](#order)
  - [Report details](#report-details)
  - [Reporting Receipt](#submit-scr)

- **[M3 sample workflow](#m3sample)**

  - [Create customer order PMS001](#crt-pms)

  

# <a name="about-this-guide"></a>About this guide

### <a name="intended-audience"></a>Intended Audience

MobileFirst Configuration User Guide provides guidance for LeanSwift customers and consultants regarding understanding the basic concept, functionality and configuration of the MO Receipt Standard App. Further information about MobileFirst standard applications can be found at [www.inform3marketplace.com](http://www.inform3marketplace.com).

#### **<a name="std-func"></a>MO Receipt standard functionality**

The intended use of this app is for a user to be reporting receipts against Manufacturing orders (MOs) with a trimmed down way to quickly and easily report quantity produced.

Using PO Receipt module in MobileFirst Orders can be searched by providing order number and product number. They can also input only product number and list all orders containing the product and choose from the list.The receipt report can be done by tapping the orders in the list and on selecting valid location and manufactured quantity that order can be reported using slide to confirm at the end.

# <a name="tech-details"></a>Technical details

### <a name="item-head"></a>Get item head details

**API:** MMS200MI/Get

Input field required:

| **Field** | **Description** |
| --------- | --------------- |
| ITNO      | Item number     |
| LNCD      | Language        |

### <a name="item-by-facility"></a>Get MO List by Facility

**API:** ExportMI/Select

Query: VHWHST,VHWHHS,VHWHLO,VHFACI,VHPRNO,VHMFNO,VHMAQT,VHORQT,VHORQA,VHOROA,VHMAUN,VHWHSL,VHREND,VHBANO from MWOHED where VHFACI = '%@' and VHPRNO = '%@'

### <a name="item-by-prd"></a>Get MO List by Product Number

**API:** PMS100MI/Get

Input field required:

| Field | Description         |
| ----- | ------------------- |
| CONO  | Company             |
| PRNO  | Product Number      |
| FACI  | Facility            |
| MFNO  | Manufacturing Order |

### <a name="report-receipt"></a>Submit Report

**API:** PMS050MI/RptReceipt

Input field required:

| **Field** | **Description**                                |
| --------- | ---------------------------------------------- |
| CONO      | Company                                        |
| PRNO      | Product number                                 |
| MFNO      | Manufaturing Order Number                      |
| RPQA      | Reported Quantity in alternate unit of measure |
| MAUN      | Unit of measure                                |
| WHSL      | Location                                       |
| REND      | Flagged as Complete                            |
| STAS      | Status - balance id                            |
| BANO      | Lot Number                                     |
| FACI      | Facility                                       |



# **<a name="wrk"></a>Workflow, Screen Layouts & API Logic**

### <a name="settings"></a>Settings

Initially the MO Receipt module settings can be opened to choose warehouse and facility.

<img src="../images/MORE/settings.png" style="zoom:40%;" />



### <a name="itno"></a>Item #

In the Item number field enter manually using keyboard or scan from inbuilt camera. Item Number and Order Number can be entered or scanned from inbuilt camera.

/*Image*/

Entered details will be validated against M3 services like [Get Head](#item-head), [Get by Facility](#item-by-prd) or [Get by Order](#item-by-prd)

### <a name="order"></a>Select Order

On successfull retrival of head info data for the item number. User can select a order and can be reported.

/*Image*/

Select any line item to do the report.

### <a name="report-details"></a>Report details

After selecting an line item in the order. Enter the location and manufactured quantity.

/*Image*/

### <a name="submit-scr"></a>Reporting Receipt

All entered details will be validated and if the data were valid the slider will be shown. On slide to confirm the order receipt will be reported.

/*Image*/

# <a name="m3sample"></a>M3 Sample Flow

This section describes the MO Receipt workflow in M3 to create purchase order. The current warehouse and facility selection can be made using the search icon on the top right corner of the screen.

### <a name="crt-pms"></a>Create customer order PMS001

- Manufacture order can be created in PMS001.
- Enter Product, Product structure type.
- Product and its details will be defined in MMS001.
- On clicking [+] the order will be created this order can be viewed in PMS100 sort the list based on 70-Res/Prod/MO to see the orders.

The Product number with the manufacturing order can be searched in MO Receipt module and the receipt can be reported.