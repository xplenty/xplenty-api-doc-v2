An **invoice** specifies a bill for an account which includes pricing and charges for Xplenty services.

### Invoice Attributes

* **id** - the invoices's unique identifier
* **number** - a human readable invoice number
* **issued_at** - the date and time the invoice was created
* **notes** - placeholder for invoice notes
* **status** - the payment status for this invoice (pending, successful, failed)
* **total_cents** - the combined total of charges and credits on this invoice
* **total_currency** -the currency of the combined total
* **view_url** the invoice view url
* **created_at** - the date and time the account was created
* **updated_at** - the date and time the account was last updated
* **url** the invoice resource url (API)