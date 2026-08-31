```mermaid
graph TD
    %% 1. Vendor Registration & Renewal
    A[Vendor Registration & Renewal] --> A1[Manage initial registration & intake]
    A1 --> A2[Collect legal, tax, order, & reference docs]
    A2 --> A3[Process ongoing registration renewals]
    A3 --> B

    %% 2. Inquiry & RFQ Intake
    B[Inquiry & RFQ Intake] --> B1[Receive enquiries via Email / GeM / eProc portals]
    B1 --> B2[Circulate enquiries to PCH & TSS]
    B2 --> B3[Download tender packages]
    B3 --> C

    %% 3. Estimation & Supplier Liaison
    C[Estimation & Supplier Liaison] --> C1[Route technical & price queries to PCH & PSM]
    C1 --> C2[PSM coordinates with suppliers for quotes]
    C2 --> C3[Support receives consolidated quotes]
    C3 --> D

    %% 4. Tender Submission & Query Handling
    D[Tender Submission & Query Handling] --> D1[Upload quotations & forms on portal]
    D1 --> D2[Coordinate with Finance for EMD / Bank Guarantee]
    D2 --> D3{Any changes required wrt commercial/technical support?}
    
    D3 -- YES --> D4[Consult with TSS/PCH & provide clarifications/docs]
    D4 --> D5[Manage Reverse Auction price revisions on GeM if triggered]
    D5 --> D3
    
    D3 -- NO --> E

    %% 5. Order Review & Order Confirmation (OC)
    E[Order Review & Order Confirmation] --> E1[Perform contract review on received PO]
    E1 --> E2[Confirm validity & execution feasibility with PSM]
    E2 --> E3[Generate Order Confirmation in system]
    E3 --> E4[Issue Proforma Invoice via PCH if advance payment required]
    E4 --> F

    %% 6. PO Placement & Delivery Scheduling
    F[PO Placement & Delivery Scheduling] --> F1[PSM extracts OC data & places POs with suppliers]
    F1 --> F2[Support updates delivery dates in OC & informs customer via PCH]
    F2 --> G

    %% 7. Dispatch & Invoicing
    G[Dispatch & Invoicing] --> G1[Receive GRN notification from logistics]
    G1 --> G2[Cross-verify line items against shipping plan]
    G2 --> G3[Instruct logistics to prepare invoice after QC pass]
    G3 --> G4[Coordinate final dispatch to customer]
