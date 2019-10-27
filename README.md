
`./src/assets/i18n` Structure and Definitions
=============================================

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

    - `DialogMessage`, displayed as the main text in
      a [`mat-dialog`](https://material.angular.io/components/dialog/)

    - `ErrorMessage`, variant of message displayed either in a error dialog OR in a input field
      [validation error](https://material.angular.io/components/input/overview#changing-when-error-messages-are-shown)

    - `SnackbarMessage`, full sentence presented in a Angular
      [`snack-bar`](https://material.angular.io/components/snack-bar/)

  - `ComponentName`, a component name reusable in various context (does not end in punctuation)

  - `ComponentHint`, a hint on what is the purpose of a component (does not end in punctuation)

  - `DialogTitle`, title of a `mat-dialog` pop-up

  - `ButtonText`, the text of a action button

  - `Placeholder`, words for a input field 
    [placeholder](https://material.angular.io/components/input/overview#placeholder)

  - `InputHint`, the hint shown under a input field,
    example: [input with hints](https://material.angular.io/components/input/examples)

  - `CheckboxLabel`, label on a [`checkbox`](https://material.angular.io/components/checkbox/)

  - `StepperLabel`, label for a "step" in a Angular Material
    [`stepper`](https://material.angular.io/components/stepper/) navigation layout

  - `ColumnName`, column name in a [`mat-table`](https://material.angular.io/components/table/)

  - `Label`, when it's no other type of label, some short text snippet somewhere in the UI

  - `SelectOption`, value displayed as an option in
    a [`mat-select`](https://material.angular.io/components/select/) element


The site that these translations are to be rendered on can be seen here:
https://pricing.sto-dev-viewspot.smithmicro.io/ (ask someone for login credentials) 


Q & A
=====

*(Below follows a list of questions and clarifications requested during processing by
the translation service.)*

---

**Question:** What does "pricing" mean? Is it the *prices of things*, or
the *action of managing prices*?

**Answer:** Managing price information cards based on phone model, for the purpose of
a mobile phone application to ask the server about it and display it on the screen.

---

**Question:** What is a "store"?

**Answer:** We use the term *Store* to refer to a mobile network operator retail outlet, where
they sell phones/gadgets and their subscription plans.

---

**Question:** What is a "card"?

**Answer:** We use the term *Price Card*— or simply *Card* —to refer to a set of prices,
"promotions", texts and attributes that are to be used to dynamically render price information on
the screen of a client device.  The price card also includes rank, requirements and validity data
that determines whether it will be the one returned by the server when client _X_ requests
"the best card for its model and location".

---

**Question:** What is a "promotion"?

**Answer:** It's a sort of ad or marketing thingy inside the client side presentation of
the price card.  *"Buy it today, the offer expires tomorrow!"*,
*"Trade in your old phone and get money for free on purchase."* et cetera.  These promotions also
have their own variations of fineprint texts, classification "tags" and other things. 

---

**Question:** What is "fineprint"?

**Answer:** The tiny legalese texts that are always there when you want to buy something as
a consumer.  E.g. *"24 mo contract period, cancellation fee $50 per month."*

---
