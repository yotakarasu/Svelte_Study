<script lang="ts">
    //カウントを管理
    let count = $state(0);

    // countが変更されたら自動実行
    $effect(() => {
        console.log('現在のカウント: ${count}');

        // ブラウザのタブタイトルを変更
        document.title = 'カウント: ${count}';
    });
</script>

<h1>$effect()の学習</h1>

<p>カウント: {count}</p>

<button onclick={() => count++}>
    カウントアップ
</button>

<button onclick={() => count = 0}>
    リセット
</button>