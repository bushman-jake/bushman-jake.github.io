<div style="background-color: {bgColor}" class="content">
    <div class="container">
        <form on:submit|preventDefault={onSubmit} id="entry-form">
            <h1>Welcome, Bushman!</h1>
            <hr />
            <fieldset>
                <legend>Enter Code</legend>
                <input bind:value={entryCode} type="text" name="code" id="entry-form-code" />
            </fieldset>
            <button type="submit">Submit</button>
        </form>
    </div>
</div>

<script>
    import { goto } from '$app/navigation';

    const CODE = "let's go"

    let entryCode = "";
    let bgColor = "#8cd19b";

    function onSubmit() {
        if (entryCode.toLowerCase() === CODE) {
            goto("/success");
        } else {
            bgColor = "#d35555";
        }
    }
</script>

<style>
    .content {
        width: 100vw;
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        background-image: url("./pattern.png");
        background-blend-mode: multiply;
        background-size: clamp(100px, 100%, 600px);
    }

    .container {
        width: clamp(100px, 80%, 800px);
        height: clamp(100px, 90%, 600px);
        display: flex;
        justify-content: center;
        align-items: center;
        background-color: #fff;
        border-radius: 20px;
        box-shadow: 0px 20px 40px rgba(1, 34, 15, 0.568);
        padding: 20px;
    }

    h1 {
        font-family: "Red Hat Display", sans-serif;
        font-optical-sizing: auto;
        font-weight: 900;
        font-style: normal;
    }

    hr {
        margin-top: 1em;
        margin-bottom: 1em;
    }

    fieldset, button, input {
        width: 100%;
        padding: 10px;
    }

    fieldset {
        padding: 0;   
    }

    legend {
        padding-inline: 5px;
        margin-inline: 10px;
    }

    button {
        margin: 10px 0;
        border: 1px solid rgb(49, 49, 49);
        outline: none;
        cursor: pointer;
    }

    button:active {
        background-color: #d2e9df;
    }

    input {
        border: none;
        outline: none;
    }
</style>