<script lang="ts">
    import {basicSetup, EditorView} from 'codemirror';
    import {getCM, vim} from "@replit/codemirror-vim"
    import { onMount } from 'svelte';
    let dom: HTMLElement; 
    let view: EditorView;
    let value = `
    toDateString();
    testint 
        hello world
testing hello world testing
    `

    onMount(() => { 
        view = new EditorView({
            doc:value,
                extensions: [
                    vim(),
                    basicSetup,
                ],
                parent: dom 
        })
        console.log(vim())
    })
    
$:{
        if(view) {

            console.log(view.state.doc.toString());
        }
    }
</script>


<div bind:this={dom} />
