---
title: Review and launch
author: windows-driver-content
description: This topic describes how to review and launch on Data Marketplace.
ms.assetid: BEE73118-87A0-4CB4-9F0F-D01221C768EC
keywords:
- Data Marketplace mobile operators, Data Marketplace mobile broadband WDK
ms.author: windowsdriverdev
ms.date: 11/13/2017
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-devices
---

# Review and launch

## Capacity planning

Share your projection on the devices you plan to ship through your OEM partnership and your expected request per second, so the Microsoft team can perform capacity planning.

## Review connectivity offer sales

Windows Dev Center has reporting dashboards that give insights into connectivity offer (IAP) sales:

- After publishing offers to the Windows Store, you can review approximate connectivity offer sales with the [**In-app product acquisition report**](https://msdn.microsoft.com/en-us/library/windows/apps/mt148538.aspx).
- You can review up-to-date reports of connectivity offer sales, refunds, and chargebacks in the [**payout section of Windows Dev Center**](https://msdn.microsoft.com/en-us/library/windows/apps/dn986925.aspx).

## Escalation process

We establish a two-way live site escalation process for mobile operators and Microsoft to work together on any customer-facing production incidents. A live site issue is any event that is not part of the standard operation of either your service or Microsoft&#39;s service, and that causes, or might cause, an interruption or a reduction to the quality of the Data Marketplace experience. Key scenarios in the Data Marketplace experience are:

- Enable the discovery and browsing of regionally specific cellular data plans using Purchase Intent Connectivity, or a Wi-Fi/Ethernet connection.
- Enable the purchase of cellular data plans through Windows Store pay-as-you-go (PAYG) experience.
- Allow customers to view remaining balance through Windows Connection Manager and/or the Paid Wi-Fi &amp; Cellular app.
- Ensure that customers can always consume purchased data when located in the relevant country.
- Share with mobile operators analytical reporting on data consumption, purchase record, and any other relevant telemetry data.

Our goal is that both mobile operator and Microsoft agree to:

- Monitor and escalate live site incidents following the process set forth within this document.
- Prior to escalation of an incident, assign the correct priority using the guidelines set forth within this document.
- Provide responses on all incidents in accordance with the maximum allowed response times associated to the incident priority as set forth within this document.

### Live site performance SLAs

This section describes service availability and expected API response times for key APIs integrated with Data Marketplace Service.

| Service Name | Description | Impact in case of incident | Included in DM MO API monitoring? | Availability | Latency |
| --- | --- | --- | --- | --- | --- |
| Core Network Services(PGW, Online Charging System, Internet access, GRX access…) | Capability to:- Access the internet for a customer with data allowance- Access Walled Garden even with data allowance = 0 | Customers will not be able to connect to the internet using cellular data plan | **No.** Mobile operators are responsible to monitor their own Core Network services. | 99.90% | N/A |
| Provisioning API (Microbalance API) | API to (de)provision microbalance / balance. API to return the balance of customer&#39;s current data plan. | Customers will not be able to browse and purchase new data plans. Customers with an active plan will not be able to consume data and view balance. | **Yes.** | 99.90% | 400ms |
| Prepaid balance management (Get Balance API) | API to return the balance of customers current data plan. This info will also be used to determine whether customers meet the necessary criteria to purchase a new plan. | Customers will not be able to browse and purchase new plans. Customers with an active plan will be unable to view balance, though they will still be able to use it for data connectivity. | **Yes.** | 99.90% | 400ms |
| MO Direct Portal | A web portal customer can access for MO Direct scenario. | Customers will not be able to engage with Mobile Operator Direct (MO Direct) experience to sign up data plans. | **Yes.**   | 99.90% | 400ms |
| xDR(CDR, SDR, TDR) | Call details record. Subscription details record. Transaction details record. | Impacts Microsoft internal business intelligence reporting and sharing insights with mobile operators. | **No.** Mobile operators are responsible to monitor its own xDR services. | N/A | N/A |

![Service performance SLAs](BUGBUG NEED IMAGE)

### Incident escalation

#### Escalation to mobile operators

 If a service interruption is detected by Microsoft, the incident will be triaged and processed based on the severity table below. For high-severity incidents, Microsoft One Store Operations Center (OSOC) will contact mobile operators. For low severity incidents, the Data Marketplace team will contact mobile operators.

| Severity | Definition | Communication SLAs |
| --- | --- | --- |
| **High** customer or business impact. | Loss of core business scenario(s):- Service complete loss for more than 30 minutes (API monitoring test fails for more than 30 min) | Escalation by phone by Microsoft OSOC
- Initial response from mobile operators is expected within 1 hour.
- Ongoing updates are expected every business day until resolution.
 |
| **Low** customer or business impact. | Impact on non-critical business scenario(s):- Reporting failures- Information request | Escalation by email by Data Marketplace
- Initial response from mobile operators is expected within 1 business day.
- Ongoing updates are expected every week until resolution.
 |

 ![Incident severity matrix](BUGBUG NEED IMAGE)

#### Escalation to Microsoft

If a service interruption is detected by network providers (including core Data Marketplace scenarios such as purchasing data plans are down for more than 30 minutes), or mobile operators&#39; services are being spammed by Data Marketplace services, mobile operators can escalate through the Microsoft Operations Center. They can identify as a partner to the Data Marketplace Services team and report a problem. They must provide details about the incident in a template that will be supplied by the Operation center to ensure we can engage the correct teams.

- For high severity incidents, escalation to Microsoft can be made by phone to the Microsoft Operations center **+1**  **425-538-9336** and an email to [**osoc@microsoft.com**](mailto:osoc@microsoft.com) **.**
- For low severity incidents, escalation to Microsoft will occur through email to [dmcellpd@microsoft.com](mailto:dmcellpd@microsoft.com).

### Services outage

#### Communication of services outage to mobile operators

Microsoft will inform mobile operators of any Microsoft network, Data Marketplace, or Windows Store service outages by telephone and email no more than 30 minutes after we first become aware of such outage.

#### Communication of services outage to Microsoft

Mobile operators must inform Microsoft of any Core Network Services outages by telephone and email no more than 30 minutes after you first become aware of such outages. All such communications should be directed by phone to Microsoft Operations center **+1**  **425-538-9336** and an email to [**osoc@microsoft.com**](mailto:osoc@microsoft.com) **.**

### Planned maintenance

Regularly scheduled or routine maintenance of the services operated by mobile operator or Microsoft Data Marketplace team which have or may have customer impact must be communicated prior through the channels defined below.

#### Communication of planned maintenance to mobile operators

Data Marketplace will communicate planned maintenance to mobile operators no later than five business days prior. Once the maintenance is completed, a notification will be sent to mobile operators.

#### Communication of planned maintenance to Microsoft

Regularly scheduled or routine maintenance of the mobile operator&#39;s Core Network Services must be communicated by email to [osoc@microsoft.com](mailto:osoc@microsoft.com) no later than five business days prior. Once the maintenance is completed, a notification will be sent to [osoc@microsoft.com](mailto:osoc@microsoft.com).

### Requesting bug fixes

**Reporting a bug** – Each team can report a bug by email to [datamartpartnersup@microsoft.com](mailto:swifipartnersup@microsoft.com), and work with their counterparts to get a bug logged.

**Getting the bug fixed** – The Data Marketplace team must triage the bug, and provide business justification/impact.

**Deploying the fix for the bug** – Once the bug has been approved to be fixed, a tentative deployment schedule will be shared and network providers will be notified by email once the fix is deployed.

## Customer support

For Store PAYG, Microsoft support will be the Tier 1 support for purchase experience and any billing or account issue related to a customer&#39;s Microsoft account. Mobile operators are responsible for any network service issues and SIM card/eSIM profile related issues.

For MO Direct, Mobile Operators are solely responsible for any customer support issues.

### Windows Store refund policy

Microsoft support handles refund for connectivity offers based on the following criteria:

- Overall one-time refund per year for each customer.
- Customer contacts Microsoft support within the first 2 hours of plan purchase.
- Customer is not able to connect to cellular data network.
- Customer falls under One Common Refund Policy scenarios, such as unauthorized purchases, accidental purchase, and so on.

Refer to Windows [App Development Agreement](https://msdn.microsoft.com/en-us/library/windows/apps/hh694058.aspx) for details on refund, reconciliation, and offset.

### Microsoft support contact

Here are the phone numbers you can share with customers in case you need to redirect them for support from Microsoft.

| **Country** | **Country Code** | **Phone Number** |
| --- | --- | --- |
| Austria | N/A | 0 8000 123 345 |
| Belgium | +32 | (0)2 503 31 13 |
| Bulgaria | N/A
+359 | (0) 2 96 57 100
0800 15 555 |
| Croatia | N/A
+385 | (0)1 7890 300
0800 300 300 |
| Cyprus | +375 | (0)22 67 4000 |
| Czech Republic | N/A
+420 | 261 197 665
841 300 300 |
| Denmark | +45 | 82 333 100 |
| Estonia | +372 | 686 8868 |
| Finland | +358 | (0)9 8171 0400 |
| France | N/A | (0)9 70 01 90 90 |
| Germany | +49 | (0)180 6 67 22 55 |
| Greece | N/A
+30 | 801 500 3000
211 12 06 500 |
| Hungary | N/A
+36 | 1 267 46 36
06 1 267 46 36 |
| Ireland | N/A | 1850 940 940 |
| Italy | +39 | 02 38 59 14 44 |
| Latvia | +371 | 78 52 152 |
| Lithuania | +370 | 52 051 151 |
| Luxembourg | +352 | 8002 43 53 |
| Malta | N/A | 800 62 037 |
| Netherlands | +31 | (0)20 500 1500 |
| Poland | +48
N/A | 801 802 000
22 594 19 99 |
| Portugal | N/A | 808 22 32 42 |
| Romania | +40
N/A | 0801 022 222
(0)21 204 70 40 |
| Slovakia | +421
N/A | 0850 111 300
259 295 888 |
| Slovenia | +386 | (0)1 585 34 49 |
| Spain | N/A | 902 197 198 |
| Sweden | +46 | (0)8 55 99 00 00 |
| United Kingdom | +44 | (0)344 800 2400 |
| United States | +1 | (800) 642 7676 |
| Canada | +1 | 877 568 2495 |

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bp_mb\p_mb%5D:%20Planning%20your%20APN%20database%20submission%20%20RELEASE:%20%281/18/2017%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")