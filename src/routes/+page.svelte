<main>
    <section>
        <div class="intro">
            <h1>Learn to code by watching others</h1>
            <p>
                See how experienced developers solve problems in real-time.
                Watching scripted tutorials is great, but understanding how
                developers think is invaluable.
            </p>
        </div>
        <div class="sign-up">
            <p class="offer box center">
                <strong>Try it for free 7 days</strong>
                then $20/mo. thereafter
            </p>
            <SignUpForm />
        </div>
    </section>
</main>

<script lang="ts">
import SignUpForm from '$lib/components/SignUpForm.svelte'

</script>

<style>
main {
    display: flex;
    flex-direction: column;
    justify-content: center;
    height: 100vh;
}

section {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 2rem;
    margin: 2rem;
}

section > * {
    flex: 1;
    min-width: 20rem;
    max-width: 34rem;
}

h1 {
    font-size: 3rem;
    font-weight: 600;
    line-height: 1.2;
    margin: 1.5rem 0;
}

p {
    line-height: 1.6;
}

.intro {
    display: flex;
    flex-direction: column;
    justify-content: center;
    font-weight: 400;
    color: var(--white);
}

.sign-up {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
}

.offer {
    background-color: var(--blue);
    color: var(--white);
    padding: 1.2rem;
}

@media (min-width: 375px) {
    /* main {
    background-image: url('$lib/assets/bg-intro-desktop.png');
} */

    .intro {
    }
}
</style>
