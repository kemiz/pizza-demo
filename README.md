# Pizza 42

## What's this all about?!
This a small exmaple app built to demonstrate the capabillities of Auth0. OAuth is an open standard for access delegation, commonly used as a way for Internet users to grant websites or applications access to their information on other websites but without giving them the passwords.


## Ok, cool! But what does is do?
- Show how a new customer can sign up and an existing customer can sign in with email/password or Google
- Ensure that if a customer signs in with either an email/password or Google, it will betreated as the same user if they use the same email address
- Require that a customer has a verified email address before any possible activity, but still be able to sign into the app
- Use Auth0 features to gather additional information about a user without prompting directly
- Use Auth0 to call the Google People API to fetch the total number of Googleconnections a user has and store that count in their user profile

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```