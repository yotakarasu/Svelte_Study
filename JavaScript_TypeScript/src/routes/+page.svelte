<script lang="ts">
    const lessons = [
        {
            title: '分割代入',
            path: '/Destructuring_Assignment'
        },
        {
            title: 'onclick oninput',
            path: 'Event_Handling'
        },
        {
            title: 'Bind_Value',
            path: '/Bind_Value'
        },
        {
            title: 'Effect',
            path: '/Effect'
        },
        {
            title: 'Dynamic_Routing',
            path: '/Dynamic_Routing'
        }
    ]
</script>

<p>学習したい単元を選択してください</p>

<ul>
    {#each lessons as lesson}
        <li>
            <a href={lesson.path}>
                {lesson.title}
            </a>
        </li>
    {/each}
</ul>