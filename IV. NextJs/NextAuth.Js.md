#### OAuth flow
- Allow your users to sign in with their favorite preexisting logins.
*how many steps?*
- General flow has 6 part
1. Ứng dụng yêu cầu truy cập vào tài nguyên dịch vụ từ người dùng.
2. (Nếu) người dùng chấp thuận → ứng dụng nhận được **giấy uỷ quyền**.
3. Ứng dụng yêu cầu mã truy cập **(access token)** từ server(API) uỷ quyền thông qua:  xác thực danh tính & **giấy uỷ quyền**.
4. Nếu danh tính & uỷ quyền hợp lệ → server(API) cung cấp access token. Hoàn tất uỷ quyền.
5. Ứng dụng yêu cầu tài nguyên từ server(API) & dùng access token xác thực.
6. Nếu truy cập hợp lệ, server(API) cung cấp tài nguyên cho ứng dụng.
## How to
*Set up or configuration*
1. Register your application at the developer portal of your provider.
2. The redirect URI (sometimes called Callback URL) should follow this format:
	```[origin]/api/auth/callback/[provider]```
	`[provider]` refers to the `id` of your provider
	Ex: ``` https://next-auth-example.vercel.app/api/auth/callback/google```
3. Add ID and Secret key to .env file
4. Now you can add the provider settings to the NextAuth.js options object.
5. When a provider was set up,  you can sign in at the following URL: `[origin]/api/auth/signin`.

## Options
*Config??*
### → authorization option
*Authorization endpoint*
*Definition? Aim?*
### → token option
*Token endpoint*
*Definition? Aim?*
### → userinfo option
*Definition? Aim?*
### → client option
*Read more at link in docs*
### → allowDangerousEmailAccountLinking option
## Using a custom provider
## Built-in providers
### → Override default options