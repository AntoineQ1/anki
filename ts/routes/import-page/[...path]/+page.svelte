<!--
Copyright: Ankitects Pty Ltd and contributors
License: GNU AGPL, version 3 or later; http://www.gnu.org/licenses/agpl.html
-->
<script lang="ts">
    import { importJsonFile } from "@generated/backend";

    import ImportPage, { type Importer } from "../ImportPage.svelte";
    import type { PageData } from "./$types";

    export let data: PageData;

    const importer = {
        doImport: () => importJsonFile({ val: data.path }, {}),
    } as Importer;
</script>

<ImportPage path={data.path} {importer} />
