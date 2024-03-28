<script lang="ts">
    import { enhance } from '$app/forms';
    import type { ActionData, PageData } from './$types';
    
    export let data: PageData;
    export let form: ActionData;
    let s ="";
</script>

<main>
    <div class="registerContainer">
        <h1>Register</h1>
        <div class="registerContainerForm">
            <form action="?/register" method="post" use:enhance>
                <div class="test">
                    <label>Username: <input type="text" name="username" class="input"></label>
                    <label>Password: <input type="password" name="password" class="input"></label>
                    <label>Repeat Password: <input type="password" name="password-repeat" class="input"></label>
                    <label>Profile Picture: <input type="text" placeholder="image url" bind:value={s} class="input"></label>
                    <label><input type="hidden" value={s} name="pic"></label>
                    <button>Log In</button>
                    {#if form?.msg}
                        <span>{form.msg}</span>
                    {/if}
                </div>
            </form>
        </div>
        <a href="/login">Already have account?</a>
    </div>
</main>

 