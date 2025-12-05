<script lang="ts">
    import "@app/styles/styles.less";
    import "@app/styles/tailwindcss.css";

    import {DefaultLayout} from "@widgets/layouts/default";

    let {children} = $props();
</script>

<DefaultLayout>
    {@render children?.()}
</DefaultLayout>