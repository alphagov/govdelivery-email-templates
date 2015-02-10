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
header and footer set in GovDelivery.

**TODO** Where do the header and footer templates live?

[2]: https://github.com/alphagov/whitehall/blob/master/lib/whitehall/gov_uk_delivery/email_formatter.rb

The templates in this repository are those that are not sent using API calls.
This includes the [Drug Safety Update][3] which is a manually triggered email
curated by the MHRA. Management of these templates used for the emails is done
in the GovDelivery admin interface.

**TODO** Where in the GovDelivery interface can these be copied to? Which
templates does each of the HTML files in this repo correspond to?

[3]: https://www.gov.uk/drug-safety-update

## Updating email templates

To update an email template, first make the changes in the GovDelivery STAGE
environment. To test the changes, trigger an email alert by publishing a
document of the relevant type in the GOV.UK preview environment.

Once you're happy with the changes, raise a pull request against this repo.

After your pull request has been reviewed and merged, make the template changes
in the GovDelivery production account.
