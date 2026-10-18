<!-- 共通のヘッダー --> 
<script lang="ts">
    import { page } from '$app/state';
</script>

<header>
    <h1>JavaScript / TypeScript 学習</h1>

    {#if page.url.pathname !== '/'} <!-- 現在のURLがトップページ "/"だった以外だけ表示-->
        <a href="/">トップページに戻る</a>
    {/if}
</header>