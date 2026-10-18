<script lang="ts">
    //入力値を管理する変数
    let name = $state('');
    let comment = $state('');  
    let food = $state('');

    // let message = $derived(name + 'の好きな食べ物は' + food + 'です' + '今は' + comment + 'をしています。');
    let message = $derived('${name}の好きな食べ物は${food}です。${comment}'); //テンプレートリテラルを使用した方が読みやすてよい

    // サンプルデータを入力
    const setSample = () => {
        name = 'からす';
        comment = 'Svelte 5を勉強しています。';
    };

    // 入力内容をクリア
    const clearInput = () => {
        name = '';
        comment = '';
        food = '';
    };
</script>

<h1>プロフィール編集アプリ</h1>

<h2>① プロフィール入力</h2>

<label for="name">名前</label>
<input 
    id="name"
    type="text"
    bind:value={name}
    placeholder="名前を入力してください"
/>

<br />

<label for="comment">自己紹介</label>
<textarea
    id="comment"
    bind:value={comment}
    placeholder="自己紹介を入力してください"
></textarea>

<br />

<label for="food">好きな食べ物</label>
<textarea
    id="food"
    bind:value={food}
    placeholder="好きな食べ物を入力してください"
></textarea>

<h2>② プレビュー</h2>

<p>名前: {name || '未入力'}</p>
<p>自己紹介: {comment || '未入力'}</p>
<p>好きな食べ物: {food || '未入力'}</p>
<!-- {#if name.length > 0 && comment.length > 0 && food.length > 0} -->
{#if name.trim() && comment.trim() && food.trim()}
    <p>{message}</p>
{/if}

<h2>② 操作</h2>

<button onclick={setSample}>
    サンプル入力
</button>

<button onclick={clearInput}>
    クリア
</button>

<p><a href="/">トップページに戻る</a></p>