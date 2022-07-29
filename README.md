### Coding Challenge

Build a React app that can **render** a form based on following **Form schema**:

### Form schema:

```json
{
  "id": "sampleForm",
  "version": "1.0.0",
  "sections": [
    {
      "id": "primaryContact",
      "label": "Primary contact",
      "description": "The primary contact person should be able to receive notices about the project.",
      "fields": [
        {
          "id": "primaryContactName",
          "label": "Primary contact name",
          "type": "text",
          "required": true,
          "placeholder": "Enter primary contact name"
        },
        {
          "id": "primaryContactEmail",
          "label": "Primary contact email",
          "type": "email",
          "required": true,
          "placeholder": "Enter primary contact email",
          "validators": [
            {
              "type": "email",
              "message": "Please enter a valid email address",
              "pattern": "^[a-zA-Z0-9.!#$%&’*+/=?^_`{|}~-]+@[a-zA-Z0-9-]+(?:\\.[a-zA-Z0-9-]+)*$"
            }
          ]
        },
        {
          "id": "primaryContactPhone",
          "label": "Primary contact phone",
          "type": "text",
          "required": true,
          "placeholder": "Enter primary contact phone number",
          "validators": [
            {
              "type": "phone",
              "message": "Please enter a valid phone number",
              "pattern": "^[0-9]{10}$"
            }
          ]
        },
        {
          "id": "primaryContactAddress",
          "label": "Primary contact Address",
          "type": "text",
          "required": true,
          "placeholder": "Enter primary contact address"
        }
      ]
    },
    {
      "id": "secondaryContact",
      "label": "Secondary contact",
      "description": "The secondary contact person should be able to receive notices about the project.",
      "fields": [
        {
          "id": "secondaryContactCheckbox",
          "label": "Do you want to add a secondary contact?",
          "type": "checkbox",
          "defaultValue": false
        },
        {
          "id": "secondaryContactName",
          "label": "Secondary contact name",
          "type": "text",
          "required": true,
          "placeholder": "Enter secondary contact name",
          "visible": {
            "field": "secondaryContactCheckbox",
            "value": true
          }
        }
      ]
    }
  ]
}
```

### Partial form data saved in local storage:

```json
{
  "primaryContact": "John Smith",
  "primaryContactEmail": "contactEmail",
  "primaryContactPhone": "1234567890",
  "primaryContactAddress": "123 Main St"
}
```

### Requirements

* Form can rehydrate from the current data saved in local storage.
* Form page can be saved and viewed offline (e.g. in a browser). User can open the application even when they are offline and view the form page.
* On form submission or value change, the form data should be validated. If validation fails, the form should not be submitted and the user should be notified.
* On form submission, if the form data is valid, it should be saved in local storage and the user should be notified.
* secondaryContactName field should be hidden if secondaryContactCheckbox is not checked.
* Custom validators should be implemented.
* You should be able to use the form schema to build the form.
* You should be able to use the form schema to validate the form data.
* You can use any libraries you want with your React app.
