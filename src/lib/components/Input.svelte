<div class={(isValid === false) ? 'invalid' : ''}>
    <div class='flex'>
        <slot />
        <img src={IconError} alt="">
    </div>
    <small>{validationMsg}</small>
</div>

<script lang="ts">
import IconError from '$lib/assets/icon-error.svg'

export let isValid: boolean;
export let validationMsg;
</script>

<style>

/* div:nth-child(3) {
    background-color: red;
} */

.flex {
    display: flex;
    border: 1px solid var(--grayish-blue);
    border-radius: 0.3rem;
}

.flex :global(input) {
    flex-grow: 1;
    outline: none;
}

.flex:focus-within {
    border-color: var(--blue);
}

img {
    display: none;
    object-fit: contain;
    margin: 1rem;
}

small {
    display: none;
    text-align: end;
    font-style: italic;
    color: var(--red);
    margin-top: 0.5rem;
}

.invalid .flex {
    border: 2px solid var(--red);
}

.invalid .flex :global(input) {
    color: var(--red);
}

.invalid .flex :global(input::placeholder) {
    visibility: hidden;
}

.invalid img {
    display: inline-block;
}

.invalid small {
    display: block;
}

</style>