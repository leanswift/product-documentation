
# Add-on for eConnect for M3

# **Material Plan**

## **Version 4.1.0**



**Table of Contents**

- [**Overview**](#overview)
- [**Environment Details**](#environment-details)
- [**Standard Features**](#standard-features)
- [**Enhancement**](#Enhancement)
- [**Bugfix**](#bugfix)

## **Overview**

 **LeanSwift eConnect for Infor M3**  is a Magento extension that provides simple yet powerful integration between the Magento eCommerce platform and Infor M3.

Extends standard Magento functionality and offers several transactions to ensure your eCommerce websites contain up-to-date information from your M3 ERP.

**Add-on Material Plan**  for eConnect provides the customers with information about current available inventory, ATP quantity and the next available date per product from M3.

## **Environment Details**

| **Environment** | **Version** |
| --- | --- |
| Magento Open source | 2.4.1 |
| Magento Community | 2.4.1 |
| eConnect | 2.3.0 |
| eConnect Base | 5.0.0 |
| Rabbitmq | 3.8.3 |
| ION Desk | 12.0 |
| PHP | 7.4.12 |
| ION-BOD package | 3.0.0 |


## **Standard Features**

All the features of Material Plan 3.1.0 remain the same in this version
Provides customers with information about current available inventory, ATP quantity and the next available date per productfrom M3

For Simple Products, ATP is displayed in,
- Product Detail Page
- Cart Page

For Configurable and Grouped Products, ATP is displayed in,
- Cart Page only

## **Enhancement**

With 20.3.0, there is a major technical architectural change in the solution. BODs from ION are now configured to be sent to a REST API in Magento, which in turn sends them to RabbitMQ for storage and processing by eConnect. In the previous versions, ION sends BODs to RabbitMQ directly.

_Note: This version is tested only on M3-Multi-tenant_

## **Bugfix**

- Cart page becomes blank if ATP value is empty
- Date fields comparison (Planning date and current date) is now done in Date format

### **Point of Contact**

- [prabhu.mano@leanswift.com](mailto:prabhu.mano@leanswift.com)
- [niranjan.b@leanswift.com](mailto:niranjan.b@leanswift.com)
- [deepthi.tadikamalla@leanswift.com](mailto:deepthi@leanswift.com)
- [srinidhi.narayanan@leanswift.com](mailto:srinidhi.narayanan@leanswift.com)
- [vaithiyanathan.paramasivam@leanswift.com](mailto:vaithiyanathan.paramasivam@leanswift.com)
- [nrithya.rajagopalan@leanswift.com](mailto:nrithya.rajagopalan@leanswift.com)

