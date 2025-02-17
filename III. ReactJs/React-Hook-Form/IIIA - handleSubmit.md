 `</> handleSubmit:` `((data: Object, e?: Event) => Promise<void>, (errors: Object, e?: Event) => Promise<void>) => Promise<void>`

- This function will receive the form data if from validation is successfull.

### Props
|Name|Type|Description|
|---|---|---|
|SubmitHandler|`(data: Object, e?: Event) => Promise<void>`|A successful callback.|
|SubmitErrorHandler|`(errors: Object, e?: Event) => Promise<void>`|An error callback.|

### Some rules
- Easily submit form asynchronously with handleSubmit.
```
handleSubmit(onSubmit)()


// You can pass an async function for asynchronous validation.
handleSubmit(async (data) => await fetchAPI(data))
```

- `disabled` inputs will appear as `undefined` values in form values. If you want to prevent users from updating an input and wish to retain the form value, you can use `readOnly` or disable the entire `<fieldset />`
    
- `handleSubmit` function will not swallow errors that occurred inside your onSubmit callback, so we recommend you to try and catch inside async request and handle those errors gracefully for your customers.

```
const onSubmit = async () => {
  // async request which may result error
  try {
    // await fetch()
  } catch (e) {
    // handle your error
  }
}

return <form onSubmit={handleSubmit(onSubmit)} />
```

Reference more at: https://react-hook-form.com/docs/useform/handlesubmit