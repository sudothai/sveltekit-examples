<script lang="ts">
    import type { PageData } from './$types'

    export let data: PageData

    $: ({ posts } = data)
</script>

<h1>Posts</h1>

<p>Showing {posts.length} posts.</p>

{#each data.posts as { slug, title}}
    <ul>
        <li>
            <a href="/posts/{slug}">{title}</a>
        </li>
    </ul>
{/each}

<!-- <script lang="ts">
    import type { Post } from '@prisma/client'

    async function getPosts() {
        const response = await fetch('api/posts')
        const posts: Post[] = await response.json()
        return posts
    }
</script>

<h1>Posts</h1>

{#await getPosts()}
    <p>Loading...</p>
{:then posts}
    <p>Showing {posts.length} posts.</p>

    {#each posts as { slug, title, content }}
        <ul>
            <li>
                <a href="/posts/{slug}">{title}</a>
            </li>
            <li>
                <a href="/posts/{slug}">{content}</a>
            </li>
        </ul>
    {/each}
{:catch error}
    <p>{error.message}</p>
{/await} -->

<!-- <script lang="ts">
    async function subscribe(event: Event) {
        const form = event.target as HTMLFormElement
        const data = new FormData(form)

        await fetch('/api/newsletter', {
            method: 'POST',
            body: data
        })
    }
</script>

<h1>Newsletter</h1>

<form on:submit|preventDefault={subscribe}>
    <input type="email" name="email">
    <button>Submit</button>
</form> -->
