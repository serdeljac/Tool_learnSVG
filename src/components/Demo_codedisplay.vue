<template>
    <div class="demo_code">
        <h2>HTML Code:</h2>
        <pre>
        <code>
            <span class="tag_open">&lt;</span>
            <span class="tag_name">svg</span>
            <div class="attr_block">
                <span class="attr_name"> height</span>
                <span>="</span>
                <div class="attr_height">{{ attr_height }}</div>
                <span>"</span>
            </div>
            <div class="attr_block">
                <span class="attr_name"> width</span>
                <span>="</span>
                <div class="attr_height">{{ attr_width }}</div>
                <span>"</span>
            </div>
            <span class="tag_close"> /></span>
        </code>
        </pre>
    </div>
</template>

<script>
    export default {
        name: "Code_Display",
        data() {
            return {
                attr_height: "600",
                attr_width: "600",
            }
        }
    }
</script>
