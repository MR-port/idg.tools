<script lang="ts">
    import LinkButton from '$shared/components/LinkButton.svelte'
    import Heading from '$shared/components/Heading.svelte'

    import { page } from '$app/stores'
</script>

<div class="flex flex-col items-center justify-center">
    {#if $page.status === 404}
        <Heading class="mb-8">Sorry, this page does not exist</Heading>
        <LinkButton href="/" variant="primary">Explore IDG.community</LinkButton>
    {:else}
        <Heading class="mb-8">Oops! Something went wrong</Heading>
        <p class="mb-8">
            <span>HTTP {$page.status} - </span>
            {$page.error?.message}
        </p>
        <LinkButton href="/" variant="primary">Explore IDG.community</LinkButton>
    {/if}
</div>
