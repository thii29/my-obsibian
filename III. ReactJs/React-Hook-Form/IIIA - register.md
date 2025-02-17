` </> register:` `(name: string, options?: RegisterOptions) => ({ ref, name, onChange, onBlur })`
- Allow to register an input or select element and apply validation rules to React Hook Form.
- Validation rules are all based on the HTML standard and also allow for custom validation methods.
### Props
|Name|Type|Description|
|---|---|---|
|`name`|string|Input's name.|
|`options`|RegisterOptions|Input's behavior.|

### Return
|Name|Type|Description|
|---|---|---|
|`ref`|React.ref|React element ref used to connect hook form to the input.|
|`name`|string|Input's name being registered.|
|`onChange`|ChangeHandler|`onChange` prop to subscribe the input change event.|
|`onBlur`|ChangeHandler|`onBlur` prop to subscribe the input blur event.|

### Options
Reference docs: https://react-hook-form.com/docs/useform/register *

### Some rules
- Name is **required** and **unique** (except native radio & check box). Input name supports both dot and bracket syntax, which allows you to easily create nested form fields.
- We are using dot syntax only for typescript usage consistency, so bracket `[]` will not work for array form value.
    ```
    register('test.0.firstName'); // ✅
    register('test[0]firstName'); // ❌
    ```
- Changing the name on each render will result in new inputs being registered. It's recommended to keep static names for each registered input.

Reference more rules at link above *

