<script lang="ts">
    import { page } from '$app/state'; // 現在表示しているページの情報を取得するためのSvelteKitのモジュール

    // サンプルユーザーデータ
    const users: Record<string, string> = {
        '101' : 'からす',
        '102' : 'すずめ',
        '103' : 'はと'
    };

    // URLからIDを取得
    let id = $derived(page.params.id); // [id] に対応するURLの値を取得できます。

    // IDに対応する名前を取得
    let userName = $derived(users[id]);
</script>

<h1>ユーザー詳細</h1>

<p>ユーザーID: {id}</p>

{#if userName}
    <p>名前: {userName}</p>
{:else}
    <p>該当するユーザーがいません</p>
{/if}

