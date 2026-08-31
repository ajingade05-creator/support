```mermaid
graph TD
    %% STAGE 1: VENDOR REGISTRATION
    Start([Start Support Workflow]) --> A1[Vendor Registration & Renewal Intake]
    A1 --> A2[Collect Legal, Tax, Order & Reference Docs]
    A2 --> A3[Process & Maintain Ongoing Registration Renewals]
    A3 --> B1

    %% STAGE 2: INQUIRY & RFQ INTAKE
    B1[RFI / RFP / Enquiry Received via Email, GeM, or eProc Portal] --> B2{Received via Public Portal / GeM?}
    B2 -- YES --> B3[Download Tender Packages & Document Sets] --> B4
    B2 -- NO --> B4[Validate all P/N, Alternatives & Errors]

    B4 --> B5{Are all P/Ns Valid?}
    B5 -- NO --> B6[Sales to contact Customer to obtain correct P/N] --> B1
    B5 -- YES --> C1

    %% STAGE 3: SUPPLIER COSTING & ESTIMATION
    C1{Approved Suppliers Available?}
    C1 -- NO --> C2[Search for Legitimate Suppliers with HOD if in Scope] --> C3
    C1 -- YES --> C3[Send RFQs to Suppliers for Requested / Alternate Parts]

    C3 --> C4{Supplier Quotations}
    C4 -- Single Supplier --> C5[Enter Supplier P/N in Costing Sheet against Customer P/N]
    C4 -- Multiple Suppliers --> C6[Compare S/N Wise Landed Costs & Part Availability]

    C5 --> C7[Prepare Costing Sheet with Lowest Quoted Line Item / Availability]
    C6 --> C7
    C7 --> C8[Verify T&C and Quote Validity with Sales Rep]
    C8 --> C9[Estimation Sends Quote to Sales Rep for Verification]
    C9 --> D1

    %% STAGE 4: TENDER SUBMISSION & COMMERCIAL QUOTE
    D1{Is it a GeM / eProc Portal Tender?}
    D1 -- YES --> D2[Apply Digital Signatures & Complete Online Form Filling]
    D2 --> D3[Coordinate with Finance for EMD / Bank Guarantee]
    D3 --> D4[Upload Quotations PDF/Excel & Submit Tender]
    D4 --> D5

    D1 -- NO --> D5[Sales Representative Forwards Quote to Customer & Follows Up]

    D5 --> D6{Changes Required wrt Commercial / Technical Support?}
    D6 -- YES --> D7[Consult Technical Team / TSS & Provide Clarifications]
    D7 --> D8{Reverse Auction Triggered on GeM?}
    D8 -- YES --> D9[Manage Reverse Auction Price Revisions] --> D6
    D8 -- NO --> D6

    D6 -- NO --> D10[Provide Status Updates to HODs]
    D10 --> D11[Send Reminders to Customer regarding Expiry of Quotes]
    D11 --> D12[Analyze Quote Status: OPEN / CLOSED / PARTIALLY CLOSED]
    D12 --> E1

    %% STAGE 5: ORDER REVIEW & ORDER CONFIRMATION (OC)
    E1{Is PO Received from Customer?}
    E1 -- NO --> D11
    E1 -- YES --> E2[Sales Sends PO to Support to Verify Terms, Conditions & P/Ns]

    E2 --> E3{Are PO Terms & Conditions Valid?}
    E3 -- NO --> E4[Support Informs Discrepancy to Sales; Sales Requests Amended PO] --> E2
    E3 -- YES --> E5[Support Checks Quote Validity with PSM]

    E5 --> E6{Is Quote Still Valid?}
    E6 -- NO --> E7[PSM Looks for Alternative Sources / Parts & Gets Customer Acceptance]
    E7 --> E8[PSM Sends New Quote to Estimation to Prepare Comparison]
    E8 --> E9[Sales Obtains Amended PO as per New Quote] --> E2

    E6 -- YES --> E10[PSM Confirms Validity to Support]
    E10 --> E11[Support Generates Order Confirmation - OC in System]
    E11 --> E12[Support Sends OC to Sales to Forward to Customer]
    E12 --> E13[Execution Team Begins Order Placement onto Supplier]

    %% STAGE 6: PO PLACEMENT & PAYMENT VERIFICATION
    E13 --> F1[Release PO to Supplier with Verified Quote T&Cs]
    F1 --> F2[Verify Payment Terms]

    F2 -- Customer Side --> F3{Payment Terms Other Than 100% After Delivery?}
    F3 -- YES --> F4[Support & Sales Request Customer to Release Agreed Advance Payment]
    F4 --> F5[Finance Confirms Receipt of Payment] --> F7
    F3 -- NO --> F7

    F2 -- Supplier Side --> F6{Supplier Payment Terms Require Advance?}
    F6 -- YES --> F8[Request Proforma Invoice - PI & OC from Supplier]
    F8 --> F9[Finance Processes Advance Payment to Supplier] --> F10
    F6 -- NO --> F10

    F7 --> F10[PSM Tracks Lead Times, Delivery Schedules & Updates OC Dates]
    F10 --> F11[Supplier Confirms Goods Are Ready to Ship]
    F11 --> F12[PSM Notifies Logistics & Passes Invoice / Packing List Details]
    F12 --> G1

    %% STAGE 7: LOGISTICS, DISPATCH & INVOICING
    G1{Shipment Weight?}
    G1 -- <= 50kg to 70kg --> G2[Appoint DHL Express via Company Account] --> G5
    G1 -- > 50kg to 70kg --> G3{Urgent Customer Deadline?}
    G3 -- Urgent --> G4[Select 1 of 2-3 Regular Forwarders for Immediate Pickup] --> G5
    G3 -- Standard --> G6[Obtain Quotes from 2-3 Freight Forwarders & Select Lowest]
    G6 --> G7{Transport Mode?}
    G7 -- Air Freight --> G5
    G7 -- Sea Freight --> G5

    G5[Shipment Arrives at Destination Warehouse] --> G8{Warehouse / Trade Zone Type?}
    G8 -- FTWZ / SEZ / EOU --> G9[Clear Duty-Free / Debited Against Customer Bond] --> G11
    G8 -- DTA --> G10[Pay Customs Duties & Transfer to Thane Warehouse] --> G11

    G11[Quality Team Inspects Package & Material] --> G12{Material / Packaging Damaged?}
    G12 -- YES --> G13[Notify PSM Team / Log Insurance Claim & Hold Goods]
    G12 -- NO --> G14[Approve & Generate Goods Receipt Note - GRN in System]

    G14 --> G15[Notify Support & Sales; Cross-Verify Pending Line Items against Shipping Plan]
    G15 --> G16[Accounts Team Prepares Outward Sales Invoice & Packing List]
    G16 --> G17{Payment Terms Met for Dispatch?}
    G17 -- NO --> G18[Hold Shipment until Payment Arrives or Get Sales Waiver Approval] --> G17
    G17 -- YES --> G19[Affix Box Labels & Repack Material]

    G19 --> G20{Customer Delivery Method?}
    G20 -- Domestic Courier --> G21[Book & Dispatch via Blue Dart / Freight Forwarders] --> G24
    G20 -- Govt Carrier --> G22[Dispatch via Speed Post / Govt Carrier] --> G24
    G20 -- Customer Pickup --> G23[Handover to Customer Appointed Carrier] --> G24

    G24[Support Sends Invoice, Packing Slip & AWB Tracking to Customer]
    G24 --> G25[Monitor Transit & Obtain Proof of Delivery - POD]
    G25 --> G26[Finance Follows Up for Receivables & Confirms Receipt]
    G26 --> EndNode([Remove Receivables from System & Close File])
