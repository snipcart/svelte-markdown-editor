<script>
    import marked from 'marked';
    let source = '# New document';
    $: markdown = marked(source);
</script>

<header class="header">
    <h1 class="header-title">Svelte powered markdown editor</h1>
</header>

<div class="markdown-editor">
    <div class="markdown-editor__left-panel">
        <textarea bind:value={source} class="markdown-editor__source"></textarea>
    </div>

    <div class="markdown-editor__right-panel">
        <div class="markdown-editor__output">{@html markdown}</div>
    </div>
</div>

<footer class="footer">
    Made with 💗 by&nbsp;<a href="https://snipcart.com">Snipcart</a>&nbsp;with&nbsp;<a href="https://svelte.dev">Svelte</a>&nbsp;and&nbsp;<a href="https://marked.js.org">Marked</a>.
</footer>

<style>
    .header {
        height: 10vh;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .header-title {
        margin: 0;
    }

    .markdown-editor {
        width: 100%;
        display: flex;
        align-items:flex-start;
        justify-content: space-evenly;
    }

    .markdown-editor__left-panel, .markdown-editor__right-panel {
        width: 50%;
        border: solid 1px black;
        height: 85vh;
    }

    .markdown-editor__right-panel {
        overflow: auto;
    }

    .markdown-editor__source {
        border: none;
        width: 100%;
        height: 100%;
    }

    .markdown-editor__source:focus {
        outline: none;
    }

    .markdown-editor__output {
        width: 100%;
        padding: 0 2em;
    }

    .footer {
        height: 5vh;
        display: flex;
        align-items: center;
        justify-content: center;
    }
</style>