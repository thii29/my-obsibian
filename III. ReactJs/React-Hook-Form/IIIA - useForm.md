  ` </> useForm:` [`UseFormProps`] 
 - It is a custom hook for managing forms with ease. It takes one object as **optional** argument.

### Generic Props: 
**mode:** `onChange | onBlur | onSubmit | onTouched | all = 'onSubmit' `
- validation strategy before submitting behaviour.
- validation occurs during the `onSubmit` event, which is triggered by invoking the [[IIIA - handleSubmit]] function.

**reValidateMode: **  ` onChange | onBlur | onSubmit = 'onChange' `
- validation strategy after submitting behaviour.
- when to re-validate inputs with errors after form submission, defaulting to re-validate on input change.

**defaultValues:** `FieldValues | () => Promise<FieldValues>`
- default value for the form.
- supports both synchronous and asynchronous assigment of default values.
- should avoid **undefined** as a default values.

**values:** `FieldValues`
- Reactive values to update the form values.

**errors:**  `FieldErors` 
- Reactive errors to update the form errors.

**resetOptions:** 
- Option to reset form state update while updating new form values.
- Invoked internally the reset API while `values` or `defaltValues` are updated.

**disabled:** `boolean = false`
- Disable the entire form with all associated inputs.
- If it true, preventing user interaction during asynchronous tasks or other situations where inputs should be temporarily unresponsive

### Schema validation props:
- resolver: Integrates with your preferred schema validation library.
- context: A context object to supply for your schema validations.