# Billing Instructions

The **"Billing Instructions"** section is a mechanism that defines **“who pays what and how much”** for a reservation. Instead of manually transferring charges from one account to another, you create rules that generate the necessary bills, automatically allocate the amounts, and produce the appropriate billing documents.

Through a set of options — such as specifying for whom you want to create bills, which services/charges should be included in each bill, along with multiple additional filters and automatic charge splitting — you can create rules capable of covering any complex billing requirement.

<figure><img src="../../../.gitbook/assets/image (62).png" alt=""><figcaption></figcaption></figure>

Each **“Billing Instruction”** consists of one or more **“Billing Targets”** along with some additional fields.

<figure><img src="../../../.gitbook/assets/image (63).png" alt=""><figcaption></figcaption></figure>

* **Name:** The general name of the rule (e.g. “Group Reservation with Extras”).
* **Active:** Whether this billing instruction is active.
* **Default:** Whether it is the default billing instruction.
* **Auto apply:** Whether this billing instruction is automatically applied to a reservation, depending on the reservation’s source, source segment, contact, business, agent, or contract.
* **Billing Targets:** Each billing target defines the accounts that will be created, who the recipient is (contact, booker, company, etc.), and which charges will be included. A billing instruction may contain multiple Billing Targets (e.g. one for the company, one for the guest, and one for the accommodation tax).

Let’s look at two common examples of complex billing, which you can easily handle using routing and apply to any reservation that should follow the rule.

**Example 1: Group Reservation**

We have a group booking with 8 rooms.

We want all room charges to be invoiced to the travel agency with a service invoice (ΤΠΥ).

We want the accommodation taxes to be invoiced separately to the main guest of each room with a receipt (ΕΣΤΑ).

We also want all other charges to be invoiced separately to the main guest of each room with a retail receipt (ΑΠΥ).

<figure><img src="../../../.gitbook/assets/image (64).png" alt=""><figcaption></figcaption></figure>

**Example 2: Social Tourism**

We have a reservation with a social tourism voucher.

It covers a specific amount per night for a defined number of nights.

We want the accommodation amount covered by the voucher to be invoiced to the voucher provider with a service invoice (ΤΠΥ).

We want the remaining accommodation amount, as well as the accommodation taxes, to be invoiced to the guest with a retail receipt (ΑΠΥ) and accommodation tax receipt (ΕΣΤΑ), respectively.

<figure><img src="../../../.gitbook/assets/image (65).png" alt=""><figcaption></figcaption></figure>

### **Billing Target**

In the Billing Target section, you define the structure of the account, the recipient, and the charges it will include.

Each Billing Target has its own Billing Scope (Billing Level: group invoice, per reservation, or per room), the recipient type (contact, booker, company, etc.), and its own Rules, which determine which charge categories it covers (arrangement, extras & incidentals, complimentary, etc.).Each Billing Target supports additional filters and split settings to further refine the output.

<div align="left"><figure><img src="../../../.gitbook/assets/image (66).png" alt=""><figcaption></figcaption></figure></div>

**Billing Scope**

The Billing Scope defines how charges will be grouped.

* **Group Bill:** Creates a single consolidated invoice for the entire group.
* **Reservation Bill:** Creates one invoice per reservation.
* **Accommodation Bill:** Creates separate invoices for each accommodation unit/room.

**Billing To:** Defines the counterparty for each invoice (Contact, Booker, Agent, Business, Primary Guest, Other Contact, Other Business).

**Invoice Resolution Mode:** Defines how the system determines the type of document to be issued.

* **Auto-detect invoice type:** The system selects the invoice type based on the recipient’s profile (e.g. an invoice for companies, a receipt for individuals). Additional configuration fields are available, such as invoice type, secondary invoice type, and allowed customer type (company or all).
* **Specific invoice type:** Provides a manual selection field for choosing a specific document type (e.g. service invoice (ΤΠΥ), retail receipt (ΑΠΥ), or Special Climate Resilience Fee document).

**Charge Categories:** Here you select which charge categories will be included by this target.

<div align="left"><figure><img src="../../../.gitbook/assets/image (67).png" alt=""><figcaption></figcaption></figure></div>

* **All:** Selects all charges from all categories.
* **Room Only:** Only the net accommodation amount (excluding meals or taxes).
* **F\&B Room Charges:** Charges from restaurants/bars that have been posted to the room.
* **Stay/City Taxes:** The accommodation tax or climate resilience fee.
* **Complimentary:** Zero-value charges (complimentary services).
* **Tips:** Gratuities charged to the room.
* **Arrangement:** Refers to the overall accommodation package (e.g. Bed & Breakfast or Half Board).
* **Extra Meals:** Meals outside the included package.
* **Extras & Incidentals:** Minibar, laundry, telephone charges, etc.
* **Other Fees:** Various additional charges (e.g. late check-out fee).
* **Day Use:** Charges for daytime room usage.
* **Rest / Unclassified:** Any charges not mapped to the above categories.



### Additional Filters

Next to each charge category, as well as the Billing Target, there is a filter icon that provides even greater control over charge selection, offering additional filtering options.

<div align="left"><figure><img src="../../../.gitbook/assets/image (68).png" alt=""><figcaption></figcaption></figure></div>

**Service & Stay Filters**&#x20;

Here you restrict the rule using additional basic filters.

* **Service:** Select specific services (e.g. only “Breakfast” and not the full Arrangement).
* **Source:** The rule applies only to reservations from a specific source (e.g. only bookings from Booking.com or Expedia).
* **Room Types:** Restricts the rule to specific room types (e.g. only Junior Suites).
* **Rooms:** Applies only to specific room numbers.
* **Extras:** Filters based on specific additional services added to the reservation.

**Stay Rules**&#x20;

Here you define time-based restrictions for the duration of the reservation.

* **MIN LENGTH OF STAY:** The rule is applied only if the reservation has at least this number of nights.
* **MAX LENGTH OF STAY:** The rule stops applying if the reservation exceeds this number of nights.
* **MAX NIGHTS:** Defines the maximum number of nights covered by this billing target (e.g. the company pays only the first 2 nights).

**Date Filters**&#x20;

They allow routing of charges based on **when** something occurs.

* **CHARGE DUE DATE (From/To):** Filters based on the date when the charge becomes due.
* **MIN/MAX STAY DATE:** Refers to dates within the stay. Useful if you want to charge someone only for consumption that occurred, for example, during the weekend.
* **ARRIVAL / DEPARTURE DATE:** The rule applies only to reservations with specific arrival or departure dates (e.g. for a particular conference).

**Amount Rules**&#x20;

They define financial limits for routing.

* **MIN MATCHED AMOUNT:** The charge must exceed this amount in order to be assigned to this account.
* **MAX MATCHED AMOUNT:** The maximum total amount this billing target can accept. Any amount exceeding this limit will be routed to the next Billing Target.

### Split Configuration

Allows splitting a charge between two or more Billing Targets. You can define that a recipient covers only a percentage, a daily allowance, or a total allowance, with any remaining amount automatically being assigned to the next Billing Target.

<div align="left"><figure><img src="../../../.gitbook/assets/image (69).png" alt=""><figcaption></figcaption></figure></div>

* **None:** No split is applied.
* **Total Percentage:** Percentage-based split (e.g. the company pays 50% of the accommodation).
* **Daily Allowance:** Daily limit (e.g. the company covers up to €100/day, and the guest pays the rest).
* **Total Allowance:** Overall limit for the entire stay.

### **Payment Settings**

Here you configure how the charges routed to this specific Billing Target will be settled.

<div align="left"><figure><img src="../../../.gitbook/assets/image (70).png" alt=""><figcaption></figcaption></figure></div>



* **All (Reservations & Customer Account):** Search everywhere
* **Reservation:** Search only within reservations
* **Room:** Search within accommodation deposits
* **Customer Account:** Search within the customer balance
* **Third Party:** Search in external/third-party sources
* **With Credit:** Credit is allowed
* **No Payment:** No payment is required

### **Application and Use of Billing Instructions**

You can apply a Billing Instruction Rule to a reservation in four ways:

* **From within the reservation (Additional Information):** In the _Billing Instructions_ field, select the rule you want to apply.
* **From within the reservation (Accounts & Invoices tab):** The _Instructions_ button in the top right, next to the _Start Billing Wizard_ button, opens a form where you can select a rule or view the currently selected one. The same form also allows you to edit the rule or create a custom variation for the specific reservation only.
* **Using the Start Billing Wizard:** In the _Billing Selection_ field, choose _Bill Instructions_. In the _Bill Instruction_ field that appears below, select the desired rule. If the reservation already has a Billing Instruction assigned, it will be shown as the default selection.
* **Bulk assignment from the reservation list:** You can assign Billing Instructions to multiple reservations at once from the reservations list.



To generate the invoices based on the selected rule, choose **“Issue All”** from the _Accounts & Invoices_ tab of the reservation, or **“Create Accounts”** within the billing wizard.

<figure><img src="../../../.gitbook/assets/image (71).png" alt=""><figcaption></figcaption></figure>

> Even after applying a rule and generating the accounts, you can still intervene and make any manual changes or corrections up until the moment you proceed with issuing the invoices.
