<form class="input box center" on:submit={submit}>
    <Input isValid={firstNameValid} validationMsg={firstNameValidatorMsg}>
        <input
            type="text"
            name="first-name"
            placeholder="First Name"
            on:change={firstNameValidator}
            bind:value={firstName}
        />
    </Input>
    <Input isValid={lastNameValid} validationMsg={lastNameValidatorMsg}>
        <input
            type="text"
            name="last-name"
            placeholder="Last Name"
            on:change={lastNameValidator}
            bind:value={lastName}
        />
    </Input>
    <Input isValid={emailValid} validationMsg={emailValidatorMsg}>
        <input
            type="text"
            name="email"
            placeholder="Email Address"
            on:change={emailValidator}
            bind:value={email}
        />
    </Input>
    <Input isValid={passwordValid} validationMsg={passwordValidatorMsg}>
        <input
            type="password"
            name="password"
            placeholder="Password"
            on:change={passwordValidator}
            bind:value={password}
        />
    </Input>
    <input
        type="submit"
        name="submit"
        value="Claim your free trial"
    />
    <small>
        By clicking the button you are agreeing to out
        <a href="">Terms and Services</a>
    </small>
</form>

<script lang="ts">
import Input from '$lib/components/Input.svelte'

let firstName: string;
let lastName: string;
let email: string;
let password: string;

let firstNameValid: boolean;
let lastNameValid: boolean;
let emailValid: boolean;
let passwordValid: boolean;

const firstNameValidatorMsg = "First Name cannot be empty";
const lastNameValidatorMsg = "Last Name cannot be empty";
let emailValidatorMsg = "Email cannot be empty";
const passwordValidatorMsg = "Password cannot be empty";

function firstNameValidator() {
    if (firstName === '' || firstName === undefined) {
        firstNameValid = false;
    } else {
        firstNameValid = true;
    }
}

function lastNameValidator() {
    if (lastName === '' || lastName === undefined) {
        lastNameValid = false;
    } else {
        lastNameValid = true;
    }
}

function emailValidator() {
    email = email?.trim();
    if (email === '' || email === undefined) {
        emailValidatorMsg = "Email cannot be empty";
        emailValid = false;
    } else if (/^[\w!#$%&'*+/=?`{|}~^-]+(?:\.[\w!#$%&'*+/=?`{|}~^-]+)*@(?:[a-zA-Z0-9-]+\.)+[a-zA-Z]{2,6}$/.test(email)) {
        emailValid = true;
    } else {
        emailValidatorMsg = 'Looks like this is not an email';
        emailValid = false;
    }
}

function passwordValidator() {
    if (password === '' || password === undefined) {
        passwordValid = false;
    } else {
        passwordValid = true;
    }
}

function submit() {
    firstNameValidator();
    lastNameValidator();
    emailValidator();
    passwordValidator();
}

</script>

<style>
form {
    display: flex;
    flex-direction: column;
    gap: 1.2rem;
    background-color: var(--white);
    padding: 2.5rem;
}

input {
    border: none;
    border-radius: 0.3rem;
    padding: 1.2rem 1.8rem;
    font-weight: 600;
    color: var(--dark-blue);
}

input[type="submit"] {
    background-color: var(--green);
    color: var(--white);
    border: none;
    text-transform: uppercase;
    font-weight: 500;
    letter-spacing: 2px;
    box-shadow: 0 4px 0 var(--green-shadow);
}

form small {
    color: var(--grayish-blue);
    font-weight: 500;
}


</style>