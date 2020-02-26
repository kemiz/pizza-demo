<template>
  <div class="about">
    <br>
    <h1>What's this all about?!</h1>
    <p class="main-text">This a small exmaple app built to demonstrate the capabillities of Auth0. OAuth is an open standard for access delegation, commonly used as a way for Internet users to grant websites or applications access to their information on other websites but without giving them the passwords.</p>
    <br>
    <h2>Ok, cool! But what does is do?</h2>
    <div class="bullet-div">
      <ul class="bullet">
        <li class="bullet-text">Show how a new customer can sign up and an existing customer can sign in with email/password or Google</li>
        <li class="bullet-text">Ensure that if a customer signs in with either an email/password or Google, it will betreated as the same user if they use the same email address</li>
        <li class="bullet-text">Show that the solution can be built as a “modern” web application (SPA) which can thensecurely call the API backend of Pizza 42 using OAuth.</li>
        <li class="bullet-text">Require that a customer has a verified email address before they can place a pizza order, but still be able to sign into the app.</li>
        <li class="bullet-text">Use Auth0 features to gather additional information about a user without prompting  directly.</li>
        <li class="bullet-text">Use Auth0 to call the Google People API to fetch the total number of Googleconnections a user has and store that count in their user profile.</li>
      </ul>
    </div>
  </div>
</template>

<style scoped>
.main-text {
  margin: 20px;
  padding-left: 10%;
  padding-right: 10%;
  text-align: justify;
}

.bullet-text {
  margin: 20px;
  text-align: left;
}

.bulllet-div {
  padding-left: 10%;
  padding-right: 10%;
}

ul.bullets {
  list-style-type: square;
  list-style-position: inside;
}

</style>
