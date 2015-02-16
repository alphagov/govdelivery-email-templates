GovDelivery email templates
===========================

Email alerts for GOV.UK are sent via GovDelivery.

Some templates are set in API calls. Some templates are set in GovDelivery.
Some templates are a mix of content set in an API call and headers/footers set
in GovDelivery.

The templates in this repository are those that are not sent using API calls.
Management of these templates used for the emails is done in the GovDelivery
admin interface.

### Specialist Publisher

Specialist Publisher sets [templates in API calls][1] for most of the
specialist formats it publishes. All changes should be made in that
application.

[1]: https://github.com/alphagov/specialist-publisher/tree/master/app/views/email_alerts

### Whitehall

Whitehall sets [templates in API calls for the body of emails][2], and uses a
header and footer set in GovDelivery.

- The header image is controlled by setting the default banner in: _Templates >
  Banners_
- The footer is controlled by setting the default footer in: _Accounts
  > Footers_

[2]: https://github.com/alphagov/whitehall/blob/master/lib/whitehall/gov_uk_delivery/email_formatter.rb

### Drug Safety Update

The entirety of the [Drug Safety Update][3] email including header, body and
footer are in `drug_safety_update.html`. This template can be found in
GovDelivery in the GOV.UK account: _Templates > Advanced Bulletin > Advanced
Layouts > Drug Safety Update_

The HTML markup from the template should be copied into the "Container Setup"
field, and the CSS should be copied into the "Inline CSS" field.

The `drug_safety_update_static.html` file contains the same layout as
`drug_safety_update.html`, filled with example content for previewing in a
browser.

[3]: https://www.gov.uk/drug-safety-update

## Updating email templates

To update an email template, first make the changes in the GovDelivery STAGE
environment. To test the changes, trigger an email alert by publishing a
document of the relevant type in the GOV.UK preview environment.

Once you're happy with the changes, raise a pull request against this repo.

After your pull request has been reviewed and merged, make the template changes
in the GovDelivery production account.

## TODO

- Add the Whitehall header image and footer code into this repository
- Add information and templates for Foreign Travel Advice emails
