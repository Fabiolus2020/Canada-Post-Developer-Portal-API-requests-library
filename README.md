# Canada Post API Insomnia Collections

![API](https://img.shields.io/badge/API-REST-blue) ![Authentication](https://img.shields.io/badge/Auth-OAuth%202.0-green) ![Insomnia](https://img.shields.io/badge/Client-Insomnia-6f42c1) ![Format](https://img.shields.io/badge/Format-YAML-orange)

## Overview

This repository contains importable **Insomnia REST collections** for testing Canada Post Developer Portal APIs in two integration models:

- **Merchant scenarios** — requests executed by an individual merchant using its own credentials and account information.
- **Platform scenarios** — requests executed by an ecommerce platform or technology partner supporting merchant integrations.

The current functional collections contain **240 Merchant requests** and **245 Platform requests**, representing **114 unique method-and-endpoint combinations**. Counts include separate test scenarios that may call the same endpoint with different payloads, options, or expected outcomes.

## Repository structure

```text
Merchant_Scenarios/
├── 10_Customer_Information_Insomnia_2026-07-14.yaml
├── 1_Merchant_Scenarios_Insomnia_All_2026-05-28.yaml
├── 2_API_Authentication_Insomnia_2026-07-14.yaml
├── 3_Service_info_Insomnia_2026-07-14.yaml
├── 4_Tracking_Insomnia_2026-07-14.yaml
├── 5_Rating_Insomnia_2026-07-14.yaml
├── 6_Shipping_Insomnia_2026-07-14.yaml
├── 7_Post_Office_Insomnia_2026-07-14.yaml
├── 8_Return_Insomnia_2026-07-14.yaml
├── 9_PickUp_Insomnia_2026-07-14.yaml
Platform_Scenarios/
├── 10_Customer_Information_Insomnia_2026-07-14.yaml
├── 1_Platform_Scenario_Insomnia_All_2026-05-28.yaml
├── 2_API_Authentication_Insomnia_2026-07-14.yaml
├── 3_Service_Info_Insomnia_2026-07-14.yaml
├── 4_Tracking_Insomnia_2026-07-14.yaml
├── 5_Rating_Insomnia_2026-07-14.yaml
├── 6_Shipping_Insomnia_2026-07-14.yaml
├── 7_Post_Office_Insomnia_2026-07-14.yaml
├── 8_Return_Insomnia_2026-07-14.yaml
├── 9_Pick_Up_Insomnia_2026-07-14.yaml
└── README.md
```

The files beginning with `1_` are complete bundled collections. The numbered functional files provide smaller imports for focused testing. The API catalog below is generated from the newer functional files dated **2026-07-14** to avoid double-counting requests from the bundled collections dated **2026-05-28**.

## Getting started

### Prerequisites

- Insomnia with YAML import support
- Valid Developer Portal credentials and API permissions
- Merchant, platform, customer, contract, or account identifiers required by the selected scenario
- Access to the appropriate test or production API environment

### Import a collection

1. Download or clone this repository.
2. Open Insomnia and select **Import**.
3. Choose **File** and select either a complete collection or a functional YAML file.
4. Review the imported environment before executing requests.
5. Obtain an OAuth 2.0 access token using the authentication collection.
6. Replace sample identifiers and payload values with values valid for your test account.

## Configuration and security

The collections reference Insomnia environment variables such as `base_url` and `accessToken`, together with scenario-specific account values. Variable names can differ by collection, so review the imported environment and request templates before execution.

> [!IMPORTANT]
> Never commit client secrets, passwords, access tokens, production customer numbers, contract numbers, or other confidential account data. Keep secrets in private Insomnia environments or another approved secrets-management solution.

## Collection summary

| Scenario | Functional area | File | Requests |
|---|---|---|---:|
| Merchant | Customer Information | `Merchant_Scenarios/10_Customer_Information_Insomnia_2026-07-14.yaml` | 2 |
| Merchant | API Authentication | `Merchant_Scenarios/2_API_Authentication_Insomnia_2026-07-14.yaml` | 1 |
| Merchant | Service info | `Merchant_Scenarios/3_Service_info_Insomnia_2026-07-14.yaml` | 1 |
| Merchant | Tracking | `Merchant_Scenarios/4_Tracking_Insomnia_2026-07-14.yaml` | 6 |
| Merchant | Rating | `Merchant_Scenarios/5_Rating_Insomnia_2026-07-14.yaml` | 9 |
| Merchant | Shipping | `Merchant_Scenarios/6_Shipping_Insomnia_2026-07-14.yaml` | 194 |
| Merchant | Post Office | `Merchant_Scenarios/7_Post_Office_Insomnia_2026-07-14.yaml` | 8 |
| Merchant | Return | `Merchant_Scenarios/8_Return_Insomnia_2026-07-14.yaml` | 10 |
| Merchant | PickUp | `Merchant_Scenarios/9_PickUp_Insomnia_2026-07-14.yaml` | 9 |
| Platform | Customer Information | `Platform_Scenarios/10_Customer_Information_Insomnia_2026-07-14.yaml` | 2 |
| Platform | API Authentication | `Platform_Scenarios/2_API_Authentication_Insomnia_2026-07-14.yaml` | 1 |
| Platform | Service Info | `Platform_Scenarios/3_Service_Info_Insomnia_2026-07-14.yaml` | 1 |
| Platform | Tracking | `Platform_Scenarios/4_Tracking_Insomnia_2026-07-14.yaml` | 6 |
| Platform | Rating | `Platform_Scenarios/5_Rating_Insomnia_2026-07-14.yaml` | 9 |
| Platform | Shipping | `Platform_Scenarios/6_Shipping_Insomnia_2026-07-14.yaml` | 199 |
| Platform | Post Office | `Platform_Scenarios/7_Post_Office_Insomnia_2026-07-14.yaml` | 8 |
| Platform | Return | `Platform_Scenarios/8_Return_Insomnia_2026-07-14.yaml` | 10 |
| Platform | Pick Up | `Platform_Scenarios/9_Pick_Up_Insomnia_2026-07-14.yaml` | 9 |

## API request catalog

The tables list every request in the focused functional collections. Repeated endpoints are intentional when the collection includes different payloads, shipping services, options, countries, success paths, or error scenarios.

### Merchant scenarios

<details>
<summary><strong>Customer Information</strong> — 2 requests</summary>

Source: `Merchant_Scenarios/10_Customer_Information_Insomnia_2026-07-14.yaml`

| # | Request | Method | Endpoint |
|---:|---|:---:|---|
| 1 | Get Customer Information | **GET** | `/customerinfo/v1/customers/{{ _.mailby }}` |
| 2 | GetMOBOCustomerInformation | **GET** | `/customerinfo/v1/customers/{{ _.mailby }}/behalfof/{{ _.mobo }}` |

</details>

<details>
<summary><strong>API Authentication</strong> — 1 requests</summary>

Source: `Merchant_Scenarios/2_API_Authentication_Insomnia_2026-07-14.yaml`

| # | Request | Method | Endpoint |
|---:|---|:---:|---|
| 1 | API Authentication | **POST** | `/cpc-api-native-oauth-provider/oauth2/token` |

</details>

<details>
<summary><strong>Service info</strong> — 1 requests</summary>

Source: `Merchant_Scenarios/3_Service_info_Insomnia_2026-07-14.yaml`

| # | Request | Method | Endpoint |
|---:|---|:---:|---|
| 1 | Get service info Message Type SO | **GET** | `/serviceinfo/v1/shipments-service?message-type=SO` |

</details>

<details>
<summary><strong>Tracking</strong> — 6 requests</summary>

Source: `Merchant_Scenarios/4_Tracking_Insomnia_2026-07-14.yaml`

| # | Request | Method | Endpoint |
|---:|---|:---:|---|
| 1 | Tracking Details (PIN) | **GET** | `/tracking/v1/pins/1024023204031127/details` |
| 2 | Tracking Summary(PIN) | **GET** | `/tracking/v1/pins/7023210215628702/summaries` |
| 3 | Tracking Summary (DNC) | **GET** | `/tracking/v1/dncs/168067817265091/summaries` |
| 4 | Tracking Summary (REF) | **GET** | `/tracking/v1/refs/summaries?customer-number={{ _.mailby }}&reference-number=SPQFZT1V6V4&destination-postal-code=M9W1J1&mailing-date-from=2024-01-26&mailing-date-to=2024-01-30` |
| 5 | Tracking Details (DNC) | **GET** | `/tracking/v1/dncs/168067817265091/details` |
| 6 | Delivery Confirmation Certificate | **POST** | `/tracking/v1/create-certificate` |

</details>

<details>
<summary><strong>Rating</strong> — 9 requests</summary>

Source: `Merchant_Scenarios/5_Rating_Insomnia_2026-07-14.yaml`

| # | Request | Method | Endpoint |
|---:|---|:---:|---|
| 1 | GetRates_Canada (One Service) | **POST** | `/rating/v1/prices` |
| 2 | Discover Services_By_Country | **GET** | `/rating/v1/services?country=CA` |
| 3 | Get Option | **GET** | `/rating/v1/options/HFP` |
| 4 | GetRates_USA | **POST** | `/rating/v1/prices` |
| 5 | Get Service | **GET** | `/rating/v1/services/INT.` |
| 6 | GetRates_International | **POST** | `/rating/v1/prices` |
| 7 | GetRates_With_Promo_Code | **POST** | `/rating/v1/prices` |
| 8 | GetRates_International_Kahala_Post_Guarantee_delivery_Date | **POST** | `/rating/v1/prices` |
| 9 | GetRates_Canada (All Services) | **POST** | `/rating/v1/prices` |

</details>

<details>
<summary><strong>Shipping</strong> — 194 requests</summary>

Source: `Merchant_Scenarios/6_Shipping_Insomnia_2026-07-14.yaml`

| # | Request | Method | Endpoint |
|---:|---|:---:|---|
| 1 | CreateShipments_with_element_quickship-label-requested | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 2 | CreateShipments_that_will_be_deposited_at_a_Canada_Post_Facility | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 3 | CreateShipments_that_will_be_picked_at_your_location | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 4 | CreateShipments_Pay_By_Account | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 5 | CreateShipments_Pay_By_CreditCard | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 6 | CreateShipments_With__A_Return_label | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 7 | CreateShipments_Using_Promo_Code | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 8 | CreateShipments_with_continuous_inbound_freight_shipment | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 9 | CreateShipments_with_Coverage_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 10 | CreateShipments_with_Option_COD_And_specified_Amount | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 11 | Create_Shipments_with_Option_Hold_For_Pickup | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 12 | CreateShipments_with_Proof_Of_Age_18_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 13 | CreateShipments_with_Proof_Of_Age_19_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 14 | CreateShipments_with_Leave_At_The_Door_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 15 | CreateShipments_with_Proof_Of_Age_21_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 16 | CreateShipments_with_Do_Not_Safe_Drop_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 17 | CreateShipments_with_Deliver_To_Post_Office_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 18 | CreateShipments_with_Oversized_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 19 | CreateShipments_with_element_Unpackaged_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 20 | CreateShipments_with_Mailing_Tube_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 21 | CreateShipments_with_Show_Packaging_Instruction_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 22 | Create_Shipments_with_Option_Signature | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 23 | CreateShipments_with_option_COD_And_SpecifiedAmount_Including_ShippingCost | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 24 | CreateShipments_With_QR_Code_For_Outbound | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 25 | Get Shipment_Public_Key_Info_Retrieve_QR_Code | **GET** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments/933231773349921157/qr-code` |
| 26 | Regular_Parcel | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 27 | Expedited_Parcel | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 28 | Xpresspost_Parcel | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 29 | Priority_Parcel | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 30 | Library_Book | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 31 | Expedited_Plus_Parcel | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 32 | CreateShipments_that_will_be_deposited_at_a_Canada_Post_Facility | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 33 | CreateShipments_with_element_quickship-label-requested | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 34 | CreateShipments_with_element_ReceiptReturned | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 35 | CreateShipments_with_element_PricingInfoReturned | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 36 | CreateShipments_that_will_be_picked_at_your_location | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 37 | CreateShipments_Pay_By_Credit_Card | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 38 | CreateShipments_Pay_By_Account | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 39 | CreateShipments_With_A_Return_label | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 40 | CreateShipments_Pay_By_SupplierAccount | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 41 | CreateShipments_Using_Promo_Code | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 42 | CreateShipments_with_continuous_inbound_freight_shipment | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 43 | CreateShipments_with_Coverage_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 44 | Create_Shipments_with_Option_Hold_For_Pickup | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 45 | CreateShipments_with_Proof_Of_Age_18_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 46 | CreateShipments_with_Proof_Of_Age_21_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 47 | CreateShipments_with_Leave_At_The_Door_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 48 | CreateShipments_with_Proof_Of_Age_19_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 49 | CreateShipments_with_Do_Not_Safe_Drop_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 50 | CreateShipments_with_Deliver_To_Post_Office_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 51 | CreateShipments_with_Mailing_Tube_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 52 | CreateShipments_with_element_Unpackaged_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 53 | CreateShipments_with_Oversized_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 54 | CreateShipments_with_Show_Packaging_Instruction_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 55 | Create_Shipments_with_Option_Signature | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 56 | CreateShipments_with_Option_COD_And_specified_Amount | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 57 | CreateShipments_with_option_COD_And_SpecifiedAmount_Including_ShippingCost | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 58 | CreateShipments_With_QR_Code_For_Outbound | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 59 | Get Shipment_Public_Key_Info_Retrieve_QR_Code | **GET** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments/160121773099053772/qr-code` |
| 60 | Regular_Parcel | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 61 | Xpresspost_Parcel | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 62 | Expedited_Parcel | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 63 | Priority | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 64 | Library_Books | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 65 | Expedited_Plus_Parcel | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 66 | CreateShipments_that_will_be_picked_at_your_location | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 67 | CreateShipments_Pay_By_Credit_Card | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 68 | CreateShipments_that_will_be_deposited_at_a_Canada_Post_Facility | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 69 | CreateShipments_Pay_By_Account | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 70 | CreateShipments_Using_Promo_Code | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 71 | CreateShipments_With_Coverage_Option_Automatically_Use_Max_Allowed_Amount | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 72 | CreateShipments_With_Coverage_Option_With_Specified_Amount | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 73 | CreateShipments_With_Mailing_Tube_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 74 | CreateShipments_With_Oversized_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 75 | CreateShipments_With_Unpackaged_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 76 | CreateShipments_With_Show_Packaging_Instructions_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 77 | CreateShipments_With_Show_Postage_Rate_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 78 | CreateShipments_With_Show_Insured_Value_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 79 | Expedited_Parcel_USA_Return_At_Sender_Expense | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 80 | Expedited_Parcel_USA_Abandon | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 81 | Xpresspost_Parcel_USA_Return_At_Sender_Expense | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 82 | Xpresspost_Parcel_USA_Abandon | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 83 | Small_Packet_USA_Air_Return_To_Sender | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 84 | Tracked_Packet_USA_Return_To_Sender | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 85 | Expedited_Parcel_USA | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 86 | Xpresspost_USA | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 87 | Small_Packet_USA_Air | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 88 | Tracked_Packet_USA | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 89 | CreateShipments_US_Custom_Declaration_4_items_Or_Less | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 90 | CreateShipments_US_Custom_Declaration_8_items_Or_More | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 91 | CreateShipments_With_QR_Code_For_Outbound | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 92 | Get Shipment_Public_Key_Info_Retrieve_QR_Code | **GET** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments/933231773357756491/qr-code` |
| 93 | GetShipmentReceipt For Credit Card payment | **GET** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments/933231773424311307/receipt` |
| 94 | GetShipmentsByCustomerRequestID | **GET** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments?requestId=tdd26` |
| 95 | GetShipmentsByManifestID | **GET** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments?manifestId=933231773509253301` |
| 96 | GetShipmentsByTrackingID | **GET** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments?trackingPIN=EE001438583CA` |
| 97 | GetShipmentsByGroupID | **GET** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments?groupId=StoreABC` |
| 98 | GetShipmentsNoManifest | **GET** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments?noManifest=true&date=20260314` |
| 99 | GetShipment | **GET** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments/933231773424311307` |
| 100 | CreateShipments_that_will_be_picked_at_your_location | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 101 | CreateShipments_that_will_be_deposited_at_a_Canada_Post_Facility | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 102 | CreateShipments_Pay_By_Credit_Card | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 103 | CreateShipments_Pay_By_Account | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 104 | CreateShipments_Pay_By_SupplierAccount | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 105 | CreateShipments_with_element_ReceiptReturned | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 106 | CreateShipments_with_element_PricingInfoReturned | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 107 | CreateShipments_Using_Promo_Code | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 108 | CreateShipments_With_Coverage_Option_Automatically_Use_Max_Allowed_Amount | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 109 | CreateShipments_With_Coverage_Option_With_Specified_Amount | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 110 | CreateShipments_With_Mailing_Tube_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 111 | CreateShipments_With_Oversized_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 112 | CreateShipments_with_element_Unpackaged_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 113 | CreateShipments_With_Show_Packaging_Instructions_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 114 | CreateShipments_With_Show_Postage_Rate_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 115 | CreateShipments_With_Show_Insured_Value_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 116 | Expedited_Parcel_USA_Return_At_Sender_Expense | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 117 | Expedited_Parcel_USA_Abandon | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 118 | Xpresspost_Parcel_USA_Return_At_Sender_Expense | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 119 | Xpresspost_Parcel_USA_Abandon | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 120 | Small_Packet_USA_Air_Return_To_Sender | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 121 | Tracked_Packet_USA_Return_To_Sender | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 122 | Expedited_Parcel_USA | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 123 | Xpresspost_Parcel_USA | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 124 | Small_Packet_USA_Air | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 125 | Tracked_Packet_USA | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 126 | CreateShipments_US_Custom_Declaration_4_items_Or_Less | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 127 | CreateShipments_US_Custom_Declaration_8_items_Or_More | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 128 | CreateShipments_With_QR_Code_For_Outbound | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 129 | Get Shipment_Public_Key_Info_Retrieve_QR_Code | **GET** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments/646301773418001079/qr-code` |
| 130 | GetArtefactPDF | **GET** | `/shipping/v1/artifacts/2b2897844bd7e889/shipping/10002005374/0` |
| 131 | GetArtefactZPL | **GET** | `/shipping/v1/artifacts/2b2897844bd7e889/shipping/10002005848/0` |
| 132 | GetShipmentPrice | **GET** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments/933231773424311307/price` |
| 133 | GetShipmentDetails | **GET** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments/780501774384186774/details` |
| 134 | GetGroups | **GET** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/groups` |
| 135 | VoidShipment | **DELETE** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments/933231773511842784` |
| 136 | ShipmentRefund | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments/933231773511986962/refund` |
| 137 | GetManifests | **GET** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/manifests?from=20260312&to=20260314` |
| 138 | TransmitShipments_that_will_be_picked_at_your_location | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/manifests` |
| 139 | GetManifestDetails | **GET** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/manifests/933231773509253301/details` |
| 140 | GetManifest | **GET** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/manifests/933231773509253301` |
| 141 | TransmitShipments_And_Excluding_Shipments | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/manifests` |
| 142 | GetArtefactPDF | **GET** | `/shipping/v1/artifacts/f4afdd45b22bae36/shipping/10001624319/0` |
| 143 | TransmitShipments_that_will_be_deposited_at_a_Canada_Post_Facility | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/manifests` |
| 144 | CreateShipments_that_will_be_picked_at_your_location | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 145 | CreateShipments_that_will_be_deposited_at_a_Canada_Post_Facility | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 146 | CreateShipments_Pay_By_Credit_Card | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 147 | CreateShipments_Pay_By_Account | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 148 | CreateShipments_Using_Promo_Code | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 149 | CreateShipments_With_Coverage_Option_Automatically_Use_Max_Allowed_Amount | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mailby }}/shipments` |
| 150 | CreateShipments_With_Coverage_Option_With_Specified_Amount | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 151 | Expresspost_International_Return_At_Sender_Expense | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 152 | Expresspost_International_Abandon | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 153 | International_Parcel_Air_Return_At_Sender_Expense | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 154 | International_Parcel_Air_Abandon | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 155 | Small_Packet_International_Air_Return_To_Sender | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 156 | Tracked_Packet _International_Return_To_Sender | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 157 | International_Parcel_Surface_Return_At_Sender_Expense | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 158 | Small_Packet_International_Surface_Return_To_Sender | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 159 | International_Parcel_Surface_Abandon | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 160 | Xpresspost_International | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 161 | International_Parcel_Air | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 162 | International_Parcel_Surface | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 163 | Small_Packet_International_Air | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 164 | Small_Packet_International_Surface | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 165 | CreateShipments_Custom_Declaration_8_items_Or_More | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 166 | CreateShipments__Custom_Declaration_4_items_Or_Less | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 167 | CreateShipments_With_QR_Code_For_Outbound | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 168 | Get Shipment_Public_Key_Info_Retrieve_QR_Code | **GET** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments/646301773425453526/qr-code` |
| 169 | CreateShipments_that_will_be_picked_at_your_location | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 170 | CreateShipments_that_will_be_deposited_at_a_Canada_Post_Facility | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 171 | CreateShipments_Pay_By_Credit_Card | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 172 | CreateShipments_Pay_By_SupplierAccount | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 173 | CreateShipments_Pay_By_Account | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 174 | CreateShipments_With_Promo_Code | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 175 | CreateShipments_With_Coverage_Option_Automatically_Use_Max_Allowed_Amount | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 176 | CreateShipments_With_Coverage_Option_With_Specified_Amount | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 177 | Expresspost_International_Return_At_Sender_Expense | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 178 | Expresspost_International_Abandon | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 179 | International_Parcel_Air_Return_At_Sender_Expense | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 180 | International_Parcel_Air_Abandon | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 181 | Small_Packet_International_Air_Return_To_Sender | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 182 | Tracked_Packet _International_Return_To_Sender | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 183 | International_Parcel_Surface_Return_At_Sender_Expense | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 184 | International_Parcel_Surface_Abandon | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 185 | Small_Packet_International_Surface_Return_To_Sender | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 186 | Xpresspost_International | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 187 | International_Parcel_Air | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 188 | International_Parcel_Surface | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 189 | Small_Packet_International_Air | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 190 | Small_Packet_International_Surface | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 191 | CreateShipments_Custom_Declaration_8_items_Or_More | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 192 | CreateShipments__Custom_Declaration_4_items_Or_Less | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 193 | CreateShipments_With_QR_Code_For_Outbound | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments` |
| 194 | Get Shipment_Public_Key_Info_Retrieve_QR_Code | **GET** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipments/933231773506903053/qr-code` |

</details>

<details>
<summary><strong>Post Office</strong> — 8 requests</summary>

Source: `Merchant_Scenarios/7_Post_Office_Insomnia_2026-07-14.yaml`

| # | Request | Method | Endpoint |
|---:|---|:---:|---|
| 1 | GetNearestPostOfficeByPostalCode | **GET** | `/postoffice/v1/post-offices?maximum=50&postalCode=K0A1W0` |
| 2 | GetNearestPostOfficeByLongitude&Latitude | **GET** | `/postoffice/v1/post-offices?maximum=50&longitude=-101.32354&latitude=55.32354` |
| 3 | GetNearestPostOffice_With_D2PO=true WithPostalCode | **GET** | `/postoffice/v1/post-offices?maximum=50&d2po=true&postalCode=K2K0B1` |
| 4 | GetNearestPostOffice_With_BFLF=true WithPostalCode | **GET** | `/postoffice/v1/post-offices?maximum=50&BFLF=true&postalCode=K2K0B1` |
| 5 | GetNearestPostOfficeByLongitude&Latitude_With_D2PO=true | **GET** | `/postoffice/v1/post-offices?maximum=50&d2po=true&longitude=-101.32354&latitude=55.32354` |
| 6 | GetNearestPostOfficeByLongitude&Latitude_With_BFLF=true | **GET** | `/postoffice/v1/post-offices?maximum=50&BFLF=true&longitude=-101.32354&latitude=55.32354` |
| 7 | GetPostOfficeDetail | **GET** | `/postoffice/v1/post-offices/311545/details` |
| 8 | GetNearestPostOffice_With_Province_City_StreetName | **GET** | `/postoffice/v1/post-offices?maximum=50&d2po=true&province=ON&city=Ottawa&streetName=Riverside` |

</details>

<details>
<summary><strong>Return</strong> — 10 requests</summary>

Source: `Merchant_Scenarios/8_Return_Insomnia_2026-07-14.yaml`

| # | Request | Method | Endpoint |
|---:|---|:---:|---|
| 1 | CreateAuthorizedReturn | **POST** | `/returns/v1/{{ _.mailby }}/{{ _.mobo }}/authorized-returns` |
| 2 | CreateAuthorizedReturnAndQRCode | **POST** | `/returns/v1/{{ _.mailby }}/{{ _.mobo }}/authorized-returns` |
| 3 | CreateAuthorizedReturnAndBoxFreeLabelFree | **POST** | `/returns/v1/{{ _.mailby }}/{{ _.mobo }}/authorized-returns` |
| 4 | CreateAuthorizedReturnAndQRCodeRetailOnly | **POST** | `/returns/v1/{{ _.mailby }}/{{ _.mobo }}/authorized-returns` |
| 5 | Create Open Return Template | **POST** | `/returns/v1/{{ _.mailby }}/{{ _.mobo }}/open-returns` |
| 6 | Get Open Return Templates | **GET** | `/returns/v1/{{ _.mailby }}/{{ _.mobo }}/open-returns` |
| 7 | Retrieve Next Open Return Artifact | **GET** | `/returns/v1/{{ _.mailby }}/{{ _.mobo }}/open-returns/646301773689660661/artifact` |
| 8 | Get Open Return Template | **GET** | `/returns/v1/{{ _.mailby }}/{{ _.mobo }}/open-returns/646301773689660661` |
| 9 | Delete Open Return Template | **DELETE** | `/returns/v1/{{ _.mailby }}/{{ _.mobo }}/open-returns/933231773690859090` |
| 10 | Get Open Return Template Details | **GET** | `/returns/v1/{{ _.mailby }}/{{ _.mobo }}/open-returns/646301773689660661/details` |

</details>

<details>
<summary><strong>PickUp</strong> — 9 requests</summary>

Source: `Merchant_Scenarios/9_PickUp_Insomnia_2026-07-14.yaml`

| # | Request | Method | Endpoint |
|---:|---|:---:|---|
| 1 | Pickup Availability | **GET** | `/pickup/v1/pickup-availability/K0A1W0` |
| 2 | Pickup Price | **GET** | `/pickup/v1/{{ _.mailby }}/pickup-request/price?date=2026-03-24&contractId={{ _['contract-id'] }}&priorityFlag=true&pwwFlag=true` |
| 3 | Create Pickup | **POST** | `/pickup/v1/{{ _.mailby }}/pickup-request` |
| 4 | Create Pickup Alternate Address | **POST** | `/pickup/v1/{{ _.mailby }}/pickup-request` |
| 5 | Modify On-demand Pickup | **PUT** | `/pickup/v1/{{ _.mailby }}/pickup-request/71014334` |
| 6 | Cancel On-demand Pickup | **DELETE** | `/pickup/v1/{{ _.mailby }}/pickup-request/71006690` |
| 7 | Get All On-demand Pickups | **GET** | `/pickup/v1/{{ _.mailby }}/pickup-request` |
| 8 | Get Pickup Details | **GET** | `/pickup/v1/{{ _.mailby }}/pickup-request/71006771/details` |
| 9 | Pickup Price for Alternate Address | **GET** | `/pickup/v1/{{ _.mailby }}/pickup-request/price?date=2026-03-26&contractId={{ _['contract-id'] }}&priorityFlag=true&pwwFlag=true&alternateAddressPostalCode=K2K3N5` |

</details>

### Platform scenarios

<details>
<summary><strong>Customer Information</strong> — 2 requests</summary>

Source: `Platform_Scenarios/10_Customer_Information_Insomnia_2026-07-14.yaml`

| # | Request | Method | Endpoint |
|---:|---|:---:|---|
| 1 | Get Customer Information | **GET** | `/customerinfo/v1/customers/{{ _.mailby }}-{{ _['platform-id'] }}` |
| 2 | GetMOBOCustomerInformation | **GET** | `/customerinfo/v1/customers/{{ _.mailby }}-{{ _['platform-id'] }}/behalfof/{{ _.mobo }}` |

</details>

<details>
<summary><strong>API Authentication</strong> — 1 requests</summary>

Source: `Platform_Scenarios/2_API_Authentication_Insomnia_2026-07-14.yaml`

| # | Request | Method | Endpoint |
|---:|---|:---:|---|
| 1 | API Authentication | **POST** | `/cpc-api-native-oauth-provider/oauth2/token` |

</details>

<details>
<summary><strong>Service Info</strong> — 1 requests</summary>

Source: `Platform_Scenarios/3_Service_Info_Insomnia_2026-07-14.yaml`

| # | Request | Method | Endpoint |
|---:|---|:---:|---|
| 1 | Get service info Message Type SO | **GET** | `/serviceinfo/v1/shipments-service?message-type=SO` |

</details>

<details>
<summary><strong>Tracking</strong> — 6 requests</summary>

Source: `Platform_Scenarios/4_Tracking_Insomnia_2026-07-14.yaml`

| # | Request | Method | Endpoint |
|---:|---|:---:|---|
| 1 | Tracking Details (PIN) | **GET** | `/tracking/v1/pins/2008260400502399/details` |
| 2 | Tracking Summary(PIN) | **GET** | `/tracking/v1/pins/7023210215628702/summaries` |
| 3 | Tracking Summary (DNC) | **GET** | `/tracking/v1/dncs/168067817265091/summaries` |
| 4 | Tracking Summary (REF) | **GET** | `/tracking/v1/refs/summaries?customer-number={{ _.mailby }}&reference-number=SPQFZT1V6V4&destination-postal-code=M9W1J1&mailing-date-from=2025-02-25&mailing-date-to=2025-02-26` |
| 5 | Tracking Details (DNC) | **GET** | `/tracking/v1/dncs/168067817265091/details` |
| 6 | Delivery Confirmation Certificate | **POST** | `/tracking/v1/create-certificate` |

</details>

<details>
<summary><strong>Rating</strong> — 9 requests</summary>

Source: `Platform_Scenarios/5_Rating_Insomnia_2026-07-14.yaml`

| # | Request | Method | Endpoint |
|---:|---|:---:|---|
| 1 | GetRates_Canada(One service) | **POST** | `/rating/v1/prices` |
| 2 | Discover Services_By_Country | **GET** | `/rating/v1/services?country=CA` |
| 3 | Get Option | **GET** | `/rating/v1/options/PA21` |
| 4 | GetRates_USA | **POST** | `/rating/v1/prices` |
| 5 | Get Service | **GET** | `/rating/v1/services/USA.TP` |
| 6 | GetRates_International | **POST** | `/rating/v1/prices` |
| 7 | GetRates_With_Promo_Code | **POST** | `/rating/v1/prices` |
| 8 | GetRates_International_Kahala_Post_Guarantee_delivery_Date | **POST** | `/rating/v1/prices` |
| 9 | GetRates_Canada(All services) | **POST** | `/rating/v1/prices` |

</details>

<details>
<summary><strong>Shipping</strong> — 199 requests</summary>

Source: `Platform_Scenarios/6_Shipping_Insomnia_2026-07-14.yaml`

| # | Request | Method | Endpoint |
|---:|---|:---:|---|
| 1 | CreateShipments_with_element_quickship-label-requested | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 2 | CreateShipments_that_will_be_deposited_at_a_Canada_Post_Facility | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 3 | CreateShipments_that_will_be_picked_at_your_location | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 4 | CreateShipments_Pay_By_Account | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 5 | CreateShipments_Pay_By_CreditCard | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 6 | CreateShipments_With__A_Return_label | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 7 | CreateShipments_Using_Promo_Code | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 8 | CreateShipments_with_continuous_inbound_freight_shipment | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 9 | CreateShipments_with_Coverage_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 10 | CreateShipments_with_Option_COD_And_specified_Amount | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 11 | Create_Shipments_with_Option_Hold_For_Pickup | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 12 | CreateShipments_with_Proof_Of_Age_18_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 13 | CreateShipments_with_Proof_Of_Age_19_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 14 | CreateShipments_with_Proof_Of_Age_21_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 15 | CreateShipments_with_Leave_At_The_Door_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 16 | CreateShipments_with_Do_Not_Safe_Drop_Option | **POST** | `/shipping/v1/{{ _.mailby }}/{{ _.mobo }}/shipment` |
| 17 | CreateShipments_with_Deliver_To_Post_Office_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 18 | CreateShipments_with_Oversized_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 19 | CreateShipments_with_element_Unpackaged_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 20 | CreateShipments_with_Mailing_Tube_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 21 | CreateShipments_with_Show_Packaging_Instruction_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 22 | Create_Shipments_with_Option_Signature | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 23 | CreateShipments_with_option_COD_And_SpecifiedAmount_Including_ShippingCost | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 24 | CreateShipments_With_QR_Code_For_Outbound | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 25 | Get Shipment_Public_Key_Info_Retrieve_QR_Code | **GET** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments/780501773932802504/qr-code` |
| 26 | Regular_Parcel | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 27 | Expedited_Parcel | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 28 | Xpresspost_Parcel | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 29 | Priority_Parcel | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 30 | Library_Book | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 31 | Expedited_Plus_Parcel | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 32 | CreateShipments_that_will_be_deposited_at_a_Canada_Post_Facility | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 33 | CreateShipments_with_element_quickship-label-requested | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 34 | CreateShipments_with_element_ReceiptReturned | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 35 | CreateShipments_with_element_PricingInfoReturned | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 36 | CreateShipments_that_will_be_picked_at_your_location | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 37 | CreateShipments_Pay_By_Credit_Card | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 38 | CreateShipments_Pay_By_Account | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 39 | CreateShipments_With_A_Return_label | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 40 | CreateShipments_Pay_By_SupplierAccount | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 41 | CreateShipments_Using_Promo_Code | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 42 | CreateShipments_with_continuous_inbound_freight_shipment | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 43 | CreateShipments_with_Coverage_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 44 | Create_Shipments_with_Option_Hold_For_Pickup | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 45 | CreateShipments_with_Proof_Of_Age_18_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 46 | CreateShipments_with_Leave_At_The_Door_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 47 | CreateShipments_with_Proof_Of_Age_21_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 48 | CreateShipments_with_Proof_Of_Age_19_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 49 | CreateShipments_with_Do_Not_Safe_Drop_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 50 | CreateShipments_with_Deliver_To_Post_Office_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 51 | CreateShipments_with_Mailing_Tube_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 52 | CreateShipments_with_element_Unpackaged_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 53 | CreateShipments_with_Oversized_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 54 | CreateShipments_with_Show_Packaging_Instruction_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 55 | Create_Shipments_with_Option_Signature | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 56 | CreateShipments_with_Option_COD_And_specified_Amount | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 57 | CreateShipments_with_option_COD_And_SpecifiedAmount_Including_ShippingCost | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 58 | Get Shipment_Public_Key_Info_Retrieve_QR_Code | **GET** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments/780501773941503945/qr-code` |
| 59 | CreateShipments_With_QR_Code_For_Outbound | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 60 | Regular_Parcel | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 61 | Xpresspost_Parcel | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 62 | Expedited_Parcel | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 63 | Priority | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 64 | Library_Books | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 65 | Expedited_Plus_Parcel | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 66 | CreateShipments_that_will_be_picked_at_your_location | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 67 | CreateShipments_Pay_By_Credit_Card | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 68 | CreateShipments_that_will_be_deposited_at_a_Canada_Post_Facility | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 69 | CreateShipments_Pay_By_Account | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 70 | CreateShipments_Using_Promo_Code | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 71 | CreateShipments_With_Coverage_Option_Automatically_Use_Max_Allowed_Amount | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 72 | CreateShipments_With_Coverage_Option_With_Specified_Amount | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 73 | CreateShipments_With_Mailing_Tube_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 74 | CreateShipments_With_Oversized_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 75 | CreateShipments_With_Unpackaged_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 76 | CreateShipments_With_Show_Packaging_Instructions_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 77 | CreateShipments_With_Show_Postage_Rate_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 78 | CreateShipments_With_Show_Insured_Value_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 79 | Expedited_Parcel_USA_Return_At_Sender_Expense | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 80 | Expedited_Parcel_USA_Abandon | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 81 | Xpresspost_Parcel_USA_Return_At_Sender_Expense | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 82 | Xpresspost_Parcel_USA_Abandon | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 83 | Small_Packet_USA_Air_Return_To_Sender | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 84 | Tracked_Packet_USA_Return_To_Sender | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 85 | Expedited_Parcel_USA | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 86 | Xpresspost_USA | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 87 | Small_Packet_USA_Air | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 88 | Tracked_Packet_USA | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 89 | CreateShipments_US_Custom_Declaration_8_items_Or_More | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 90 | CreateShipments_US_Custom_Declaration_4_items_Or_Less | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 91 | CreateShipments_With_QR_Code_For_Outbound | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 92 | Get Shipment_Public_Key_Info_Retrieve_QR_Code | **GET** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments/676861774540875808/qr-code` |
| 93 | GetShipmentReceipt For Credit Card payment | **GET** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments/780501773932446409/receipt` |
| 94 | GetShipmentsByManifestID | **GET** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments?manifestId=676861775581901598` |
| 95 | GetShipmentsByCustomerRequestID | **GET** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments?requestId=testieengddfFeb092024` |
| 96 | GetShipmentsByTrackingID | **GET** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments?trackingPIN=1024023205005127` |
| 97 | GetShipmentsByGroupID | **GET** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments?groupId=StoreABC` |
| 98 | GetShipmentsNoManifest | **GET** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments?noManifest=true&date=20260330` |
| 99 | GetShipment | **GET** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments/390901778082825177` |
| 100 | CreateShipments_that_will_be_picked_at_your_location | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 101 | CreateShipments_that_will_be_deposited_at_a_Canada_Post_Facility | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 102 | CreateShipments_Pay_By_Credit_Card | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 103 | CreateShipments_Pay_By_Account | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 104 | CreateShipments_Pay_By_SupplierAccount | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 105 | CreateShipments_with_element_ReceiptReturned | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 106 | CreateShipments_with_element_PricingInfoReturned | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 107 | CreateShipments_Using_Promo_Code | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 108 | CreateShipments_With_Coverage_Option_Automatically_Use_Max_Allowed_Amount | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 109 | CreateShipments_With_Coverage_Option_With_Specified_Amount | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 110 | CreateShipments_With_Mailing_Tube_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 111 | CreateShipments_With_Oversized_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 112 | CreateShipments_with_element_Unpackaged_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 113 | CreateShipments_With_Show_Packaging_Instructions_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 114 | CreateShipments_With_Show_Postage_Rate_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 115 | CreateShipments_With_Show_Insured_Value_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 116 | Expedited_Parcel_USA_Return_At_Sender_Expense | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 117 | Expedited_Parcel_USA_Abandon | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 118 | Xpresspost_Parcel_USA_Return_At_Sender_Expense | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 119 | Xpresspost_Parcel_USA_Abandon | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 120 | Small_Packet_USA_Air_Return_To_Sender | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 121 | Tracked_Packet_USA_Return_To_Sender | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 122 | Expedited_Parcel_USA | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 123 | Xpresspost_Parcel_USA | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 124 | Tracked_Packet_USA | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 125 | Small_Packet_USA_Air | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 126 | CreateShipments_US_Custom_Declaration_4_items_Or_Less | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 127 | CreateShipments_US_Custom_Declaration_8_items_Or_More | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 128 | CreateShipments_With_QR_Code_For_Outbound | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 129 | Get Shipment_Public_Key_Info_Retrieve_QR_Code | **GET** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments/676861774979247661/qr-code` |
| 130 | GetArtefactPDF | **GET** | `/shipping/v1/artifacts/2b2897844bd7e889/shipping/10002005501/0` |
| 131 | GetArtefactZPL | **GET** | `/shipping/v1/artifacts/2b2897844bd7e889/shipping/10001617625/0` |
| 132 | GetShipmentPrice | **GET** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments/780501773932446409/price` |
| 133 | GetShipmentDetails | **GET** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments/780501773932446409/details` |
| 134 | GetGroups | **GET** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/groups` |
| 135 | VoidShipment | **DELETE** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments/780501773932446409` |
| 136 | ShipmentRefund | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments/823161699548383730/refund` |
| 137 | TransmitShipments_that_will_be_picked_at_your_location | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/manifests` |
| 138 | GetManifests | **GET** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/manifests?from=20260405&to=20260407` |
| 139 | GetManifest | **GET** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/manifests/676861775582063892` |
| 140 | GetManifestDetails | **GET** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/manifests/676861775581901598/details` |
| 141 | TransmitShipments_And_Excluding_Shipments | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/manifests` |
| 142 | GetArtefactPDF | **GET** | `/shipping/v1/artifacts/021cdb9f5a4e0f3c/shipping/10001562916/0` |
| 143 | TransmitShipments_that_will_be_deposited_at_a_Canada_Post_Facility | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/manifests` |
| 144 | CreateShipments_that_will_be_picked_at_your_location | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 145 | CreateShipments_that_will_be_deposited_at_a_Canada_Post_Facility | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 146 | CreateShipments_Pay_By_Credit_Card | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 147 | CreateShipments_Pay_By_Account | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 148 | CreateShipments_Using_Promo_Code | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 149 | CreateShipments_With_Coverage_Option_Automatically_Use_Max_Allowed_Amount | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mailby }}/shipments` |
| 150 | CreateShipments_With_Coverage_Option_With_Specified_Amount | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 151 | CreateShipments_With_Mailing_Tube_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 152 | CreateShipments_With_Oversized_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 153 | CreateShipments_With_Show_Packaging_Instructions_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 154 | CreateShipments_With_Show_Postage_Rate_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 155 | CreateShipments_With_Show_Insured_Value_Option | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 156 | Expresspost_International_Return_At_Sender_Expense | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 157 | Expresspost_International_Abandon | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 158 | International_Parcel_Air_Return_At_Sender_Expense | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 159 | International_Parcel_Air_Abandon | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 160 | Small_Packet_International_Air_Return_To_Sender | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 161 | Tracked_Packet _International_Return_To_Sender | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 162 | International_Parcel_Surface_Return_At_Sender_Expense | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 163 | Small_Packet_International_Surface_Return_To_Sender | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 164 | International_Parcel_Surface_Abandon | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 165 | Xpresspost_International | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 166 | International_Parcel_Air | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 167 | International_Parcel_Surface | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 168 | Small_Packet_International_Air | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 169 | Small_Packet_International_Surface | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 170 | CreateShipments_Custom_Declaration_8_items_Or_More | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 171 | CreateShipments__Custom_Declaration_4_items_Or_Less | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 172 | CreateShipments_With_QR_Code_For_Outbound | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 173 | Get Shipment_Public_Key_Info_Retrieve_QR_Code | **GET** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments/676861775061379754/qr-code` |
| 174 | CreateShipments_that_will_be_picked_at_your_location | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 175 | CreateShipments_that_will_be_deposited_at_a_Canada_Post_Facility | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 176 | CreateShipments_Pay_By_Credit_Card | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 177 | CreateShipments_Pay_By_SupplierAccount | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 178 | CreateShipments_Pay_By_Account | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 179 | CreateShipments_With_Promo_Code | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 180 | CreateShipments_With_Coverage_Option_Automatically_Use_Max_Allowed_Amount | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 181 | CreateShipments_With_Coverage_Option_With_Specified_Amount | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 182 | Expresspost_International_Return_At_Sender_Expense | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 183 | Expresspost_International_Abandon | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 184 | International_Parcel_Air_Return_At_Sender_Expense | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 185 | International_Parcel_Air_Abandon | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 186 | Small_Packet_International_Air_Return_To_Sender | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 187 | Tracked_Packet _International_Return_To_Sender | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 188 | International_Parcel_Surface_Return_At_Sender_Expense | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 189 | International_Parcel_Surface_Abandon | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 190 | Small_Packet_International_Surface_Return_To_Sender | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 191 | Xpresspost_International | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 192 | International_Parcel_Air | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 193 | International_Parcel_Surface | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 194 | Small_Packet_International_Air | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 195 | Small_Packet_International_Surface | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 196 | CreateShipments_Custom_Declaration_8_items_Or_More | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 197 | CreateShipments__Custom_Declaration_4_items_Or_Less | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 198 | CreateShipments_With_QR_Code_For_Outbound | **POST** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments` |
| 199 | Get Shipment_Public_Key_Info_Retrieve_QR_Code | **GET** | `/shipping/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/shipments/676861775573843539/qr-code` |

</details>

<details>
<summary><strong>Post Office</strong> — 8 requests</summary>

Source: `Platform_Scenarios/7_Post_Office_Insomnia_2026-07-14.yaml`

| # | Request | Method | Endpoint |
|---:|---|:---:|---|
| 1 | GetNearestPostOfficeByPostalCode | **GET** | `/postoffice/v1/post-offices?maximum=50&postalCode=K0A1W0` |
| 2 | GetNearestPostOfficeByLongitude&Latitude | **GET** | `/postoffice/v1/postoffice?maximum=50&longitude=-101.32354&latitude=55.32354` |
| 3 | GetNearestPostOffice_With_D2PO=true WithPostalCode | **GET** | `/postoffice/v1/post-offices?maximum=50&d2po=true&postalCode=K2K0B1` |
| 4 | GetNearestPostOffice_With_BFLF=true WithPostalCode | **GET** | `/postoffice/v1/post-offices?maximum=50&BFLF=true&postalCode=K2K0B1` |
| 5 | GetNearestPostOfficeByLongitude&Latitude_With_D2PO=true | **GET** | `/postoffice/v1/post-offices?maximum=50&d2po=true&longitude=-101.32354&latitude=55.32354` |
| 6 | GetNearestPostOfficeByLongitude&Latitude_With_BFLF=true | **GET** | `/postoffice/v1/post-offices?maximum=50&BFLF=true&longitude=-101.32354&latitude=55.32354` |
| 7 | GetPostOfficeDetail | **GET** | `/postoffice/v1/post-offices/311545/details` |
| 8 | GetNearestPostOffice_With_Province_City_StreetName | **GET** | `/postoffice/v1/post-offices?maximum=50&d2po=true&province=ON&city=Ottawa&streetName=riverside` |

</details>

<details>
<summary><strong>Return</strong> — 10 requests</summary>

Source: `Platform_Scenarios/8_Return_Insomnia_2026-07-14.yaml`

| # | Request | Method | Endpoint |
|---:|---|:---:|---|
| 1 | CreateAuthorizedReturn | **POST** | `/returns/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/authorized-returns` |
| 2 | CreateAuthorizedReturnAndQRCode | **POST** | `/returns/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/authorized-returns` |
| 3 | CreateAuthorizedReturnAndBoxFreeLabelFree | **POST** | `/returns/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/authorized-returns` |
| 4 | CreateAuthorizedReturnAndQRCodeRetailOnly | **POST** | `/returns/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/authorized-returns` |
| 5 | Create Open Return Template | **POST** | `/returns/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/open-returns` |
| 6 | Get Open Return Templates | **GET** | `/returns/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/open-returns` |
| 7 | Retrieve Next Open Return Artifact | **GET** | `/returns/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/open-returns/887051748430546292/artifact` |
| 8 | Get Open Return Template | **GET** | `/returns/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/open-returns/289661744818464275` |
| 9 | Delete Open Return Template | **DELETE** | `/returns/v1/{{ _.mailby }}/{{ _.mobo }}/open-returns/289661744818464275` |
| 10 | Get Open Return Template Details | **GET** | `/returns/v1/{{ _.mailby }}-{{ _['platform-id'] }}/{{ _.mobo }}/open-returns/887051748430546292/details` |

</details>

<details>
<summary><strong>Pick Up</strong> — 9 requests</summary>

Source: `Platform_Scenarios/9_Pick_Up_Insomnia_2026-07-14.yaml`

| # | Request | Method | Endpoint |
|---:|---|:---:|---|
| 1 | Pickup Availability | **GET** | `/pickup/v1/pickup-availability/K0A1W0` |
| 2 | Pickup Price | **GET** | `/pickup/v1/{{ _.mailby }}/pickup-request/price?date=2026-04-24&contractId={{ _['contract-id'] }}&priorityFlag=true&pwwFlag=true` |
| 3 | Create Pickup | **POST** | `/pickup/v1/{{ _.mailby }}/pickup-request` |
| 4 | Modify On-demand Pickup | **PUT** | `/pickup/v1/{{ _.mailby }}/pickup-request/71014333` |
| 5 | Create Pickup Alternate Address | **POST** | `/pickup/v1/createPickup/{{ _.mailby }}/pickup-request` |
| 6 | Cancel On-demand Pickup | **DELETE** | `/pickup/v1/{{ _.mailby }}/pickup-request/71014335` |
| 7 | Get All On Demand Pickups | **GET** | `/pickup/v1/{{ _.mailby }}/pickup-request/71014333` |
| 8 | Get Pickup Details | **GET** | `/pickup/v1/{{ _.mailby }}/pickup-request/71014335/details` |
| 9 | Pickup Price for Alternate Address | **GET** | `/pickup/v1/{{ _.mailby }}/pickup-request/price?date=2026-04-24&contractId={{ _['contract-id'] }}&priorityFlag=true&pwwFlag=true&alternateAddressPostalCode=K2K3N5` |

</details>

## Suggested execution workflow

1. Run the appropriate **API Authentication** request and confirm token creation.
2. Run **Service Information** requests to validate available products, services, options, and restrictions.
3. Validate **Rating** before shipment creation when the scenario requires a price estimate.
4. Execute **Shipping** scenarios using account and address data valid for the selected environment.
5. Validate generated shipment identifiers, labels, receipts, manifests, and related artifacts.
6. Run **Tracking**, **Pick Up**, **Return**, **Post Office**, and **Customer Information** scenarios as required.
7. Record the actual HTTP status, response, pass/fail result, and comments in the associated test evidence.

## Test evidence recommendations

For each executed request, record at minimum:

- Collection and request name
- Test date and tester
- Environment
- Input identifiers or scenario reference
- Expected HTTP status and behaviour
- Actual HTTP status and response summary
- Result: Pass, Fail, Blocked, or Not Run
- Comments and defect or incident reference

## Common response checks

| Status | Meaning | Suggested check |
|:---:|---|---|
| 200 / 201 | Successful request | Validate all required response fields and generated identifiers. |
| 204 | Successful request without a body | Confirm that the requested action completed. |
| 400 | Invalid request | Review required fields, formats, query parameters, and payload rules. |
| 401 | Authentication failure | Verify the bearer token, credentials, expiration, and target environment. |
| 403 | Authorization failure | Confirm API permissions and account or platform authorization. |
| 404 | Resource not found | Verify identifiers, endpoint path, and environment. |
| 409 | State or resource conflict | Review duplicate, lifecycle, or business-rule conditions. |
| 429 | Request limit reached | Respect retry guidance and avoid rapid repeated execution. |
| 500+ | Service-side failure | Capture correlation details and response evidence before escalation. |

## Contributing

When updating a collection:

1. Preserve the Merchant or Platform scenario distinction.
2. Use descriptive request and folder names.
3. Keep secrets and live account data out of exported files.
4. Test changed requests before committing them.
5. Update the file date or release version when publishing a revised export.
6. Regenerate this catalog when requests are added, removed, or renamed.

## Disclaimer

These collections are testing and integration aids. API availability, required fields, permissions, and business rules remain governed by the applicable Canada Post Developer Portal documentation and agreements. Review request data carefully before using a production environment.

## License

Add the license or internal-use terms applicable to this repository. No license terms were included in the supplied YAML collections.
