<script lang="ts">
    import { basicSetup, EditorView} from 'codemirror';
    import { vim } from "@replit/codemirror-vim"
    import { vimtutor} from "$lib/vimtutor"
    import { onMount } from 'svelte';
    let dom: HTMLElement; 
    let view: EditorView;

    onMount(() => { 
        view = new EditorView({
            doc:vimtutor,
                extensions: [
                    vim(),
                    basicSetup,
                ],
                parent: dom 
        })
        console.log(vim())
    })
    
</script>


<div bind:this={dom} />
