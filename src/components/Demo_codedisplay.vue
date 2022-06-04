<template>
    <div class="demo_code">
        <h2>HTML Code:</h2>
        <pre>
            <code>
                <div class="tag">
                    <span class="tag_open">&lt;svg</span>
                </div>
                <div class="attr_block">
                    <span class="attr_name">height</span>
                    <span>="</span>
                    <div class="attr_adjust">{{ attr_height }}</div>
                    <span>"</span>
                </div>
                <div class="attr_block">
                    <span class="attr_name">width</span>
                    <span>="</span>
                    <div class="attr_adjust">{{ attr_width }}</div>
                    <span>"</span>
                </div>
                <div class="attr_block">
                    <span class="attr_name">viewBox</span>
                    <span>="</span>
                    <div class="attr_adjust">{{ attr_viewbox_1 }}</div>
                    <div class="attr_adjust attr_gap">{{ attr_viewbox_2 }}</div>
                    <div class="attr_adjust attr_gap">{{ attr_viewbox_3 }}</div>
                    <div class="attr_adjust attr_gap">{{ attr_viewbox_4 }}</div>
                    <span>"</span>
                </div>
                <div class="tag">
                    <span class="tag_close"> /></span>
                </div>
                
            </code>
        </pre>
        <pre>
            <p>
                
            </p>
        </pre>
    </div>
</template>

<script>
    export default {
        name: "Code_Display",
        data() {
            return {
                attr_height: 600,
                attr_width: 800,
                attr_viewbox_1: 0,
                attr_viewbox_2: 0,
                attr_viewbox_3: 0,
                attr_viewbox_4: 0,
            }
        }
    }
</script>
