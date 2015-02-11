GovDelivery email templates
===========================

Email alerts for GOV.UK are sent via GovDelivery.

Some templates are set in API calls. Some templates are set in GovDelivery.
Some templates are a mix of content set in an API call and headers/footers set
in GovDelivery.

Specialist Publisher sets [templates in API calls][1] for most of the
specialist formats it publishes.

[1]: https://github.com/alphagov/specialist-publisher/tree/master/app/views/email_alerts

Whitehall sets [templates in API calls for the body of emails][2], and uses a
header and footer set in GovDelivery. The footer for emails from Whitehall lives here: _Accounts > GOV.UK Inside Government Stage > Footers_

Whitehall email header images are added here: _Accounts > GOV.UK Inside Government Stage > Templates > Banners_

[2]: https://github.com/alphagov/whitehall/blob/master/lib/whitehall/gov_uk_delivery/email_formatter.rb

The templates in this repository are those that are not sent using API calls.
This includes the [Drug Safety Update][3] which is a manually triggered email
curated by the MHRA. Management of these templates used for the emails is done
in the GovDelivery admin interface.

### Drug Safety Update

The entirety of the Drug Safety Update email email including header, content body and footer lives in a defined template in GovDelivery.

There are two templates in this repository for the Drug Safety Update. They are:

* * *

`drug_safety_update.html`

This is the template that is used and contains the code found in GovDelivery.
It contains the HTML, CSS and GovDelivery tags as used in GovDelivery.

* * *

`drug_safety_update_static.html`

This is purely for use in previewing the above in a browser. It does not use the GovDelivery tags and instead contains some example content in their place.

* * *

The code found in `drug_safety_update.html` lives in GovDelivery here:

_Accounts > GOV.UK Inside Government Stage > Templates > Advanced Bulletin > Advanced Layouts > Drug Safety Update_

The HTML markup from the template lives in 'Container Setup' and the CSS lives in 'Inline CSS'.

Changes should be copied here to be tested in staging and then copied across to the production GovDelivery account.

[3]: https://www.gov.uk/drug-safety-update

## Updating email templates

To update an email template, first make the changes in the GovDelivery STAGE
environment. To test the changes, trigger an email alert by publishing a
document of the relevant type in the GOV.UK preview environment.

Once you're happy with the changes, raise a pull request against this repo.

After your pull request has been reviewed and merged, make the template changes
in the GovDelivery production account.
