> Cognito
> Cognito lets you add user sign-up, sign-in, and access control to your web and mobile apps quickly and easily.

> Configure Auth Category
To start provisioning auth resources in the backend, go to your project directory and execute the command:

> amplify add auth
Enter the following when prompted:
`? Do you want to use the default authentication and security configuration?
    `Default configuration`
? How do you want users to be able to sign in?
    `Username`
? Do you want to configure advanced settings?
    `No, I am done.``

    > To push your changes to the cloud, execute the command:
* amplify push
>  Install Amplify Libraries
Add the following dependency to your app‘s build.gradle along with others you added above in Prerequisites and click “Sync Now” when prompted:
`dependencies {
    implementation 'com.amplifyframework:aws-auth-cognito:1.17.4'
}`

> Initialize Amplify Auth
 > Add the Auth plugin before calling Amplify.configure

`// Add this line, to include the Auth plugin.
Amplify.addPlugin(new AWSCognitoAuthPlugin());
Amplify.configure(getApplicationContext());`

> Check the current auth session
 * We can now check the current auth session.
 * For testing purposes, you can run this from your MainActivity’s onCreate method.

`Amplify.Auth.fetchAuthSession(
    result -> Log.i("AmplifyQuickstart", result.toString()),
    error -> Log.e("AmplifyQuickstart", error.toString())
);`


> Sign in
 > The Auth category can be used to register a user, confirm attributes like email/phone, and sign in with optional multi-factor authentication. It is set up to use Amazon Cognito User Pools which manages the users and their properties.
