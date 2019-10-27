
`./src/assets/i18n` Translation Structure and Definitions
=========================================================

The translation keys are encoded as follows,
_`<PageViewVariant><ThingInsideThePage><ElementSuffix>`_:

- The first camelCased words attempts to capture what higher-order component the text occurs in,
  e.g. _`pageHeaderSettingsMenuManageUsersButtonText`_ is to be interpreted as something located in
  the page header settings menu.  Other higher-order components are:

  - `loginPage`, the view used to authenticate the user, and also create a new password when
    a password reset is required by the system

  - `landingPage`, the landing page shown after logging in, where the user can select a *feature*
    to use (Pricing, Stores)

  - `priceMgmt`, the UI for interacting with device models and their associated price cards,
    containing ...

    - `priceMgmtModelsList`, list of device models and buttons to add/edit/delete them
      (`priceMgmtModels<Add/Edit>Device`)

    - `priceMgmtCardsList`, the list of price cards shown after selecting a device model and
      buttons to add/edit/view/delete them (`priceMgmt<AddOrEdit/View>PriceCard`)

  - `storeInfo`, the UI for uploading, mapping and viewing operator store data (_"stores that sell
    mobile phones and subscriptions"_)

  - `contentMgmt`, upcoming feature for managing content (for display on a mobile phone)

  - `pageHeader`, page top header with menu buttons for accessing settings, signing out, et cetera

  - `usersList`, view accessible via the page header action menu if you're a super admin;
    lists all users with action buttons to reset passwords, deactivate and re-activate accounts,
    also provides the `usersListCreateUser` sub-view 

  - `instangeSettingsPage`, another view accessible from page header action menu for super admins;
    enables the admin to review hard coded instance (deployment) settings, wipe all store data, and
    configure the "promotion tags" that are to be allowed in "price card promotions"

  - `storeInfoGuide`, a UI view that allows the operator to upload store data CSVs and map columns
    to data types, assign columns used for "price card target filters" and
    identify the unique store identifier

  - `auth` collects common authentication and authorization error messages that might occur
    at any time due to insufficient privileges or authorization token expiration's

  - Lastly, the `generic` prefix collects various common texts rendered in every other view, not
    tied to any specific component

- The suffix is typically _`<SomethingSomething>ButtonText`_, _`<SomethingSomething>DialogMessage`_
  et cetera, with the following meanings:
  - `HeaderText`, a HTML page header (`<h1>` tag or Angular Material `<mat-card-header>`)
  - `Message`, a full sentence ending in punctuation, typically a paragraph (`<p>`) HTML element
    - `ErrorMessage`, variant of message displayed in a error dialog or form validator
    - `DialogMessage`,
    - `SnackbarMessage`,
  - `ComponentName`, a component name reusable in various context (does not end in punctuation)
  - `ComponentHint`,
  - `DialogTitle`,
  - `ButtonText`, the text of a action button
  - `ColumnLabel`,
  - `Placeholder`,
  - `InputHint`,
  - `CheckboxLabel`,
  - `StepperLabel`,
  - `Label`,
  - `SelectOption`,

The site that these translations are to be rendered on can be seen here:
https://pricing.sto-dev-viewspot.smithmicro.io/ (ask someone for login credentials) 
