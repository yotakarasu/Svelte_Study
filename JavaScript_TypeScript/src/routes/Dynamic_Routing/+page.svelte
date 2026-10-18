<script lang="ts">
    const users = [
        { id: '101', name: 'からす' },
        { id: '102', name: 'すずめ' },
        { id: '103', name: 'はと'}
    ];
</script>

<h1>ユーザー一覧</h1>

<ul>
    {#each users as user}
        <li>
            <a href={`/Dynamic_Routing/${user.id}`}>
                {user.name}
            </a>
        </li>
    {/each}
</ul>