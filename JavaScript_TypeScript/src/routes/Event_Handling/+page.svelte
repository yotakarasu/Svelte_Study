<script lang="ts">
    // 入力中の名前
    let inputName = $state('');

    // 登録済みの名前
    let names = $state<string[]>([]);

    // 登録ボタンのクリック処理
    const addName = () => {
        const newName = inputName.trim(); //trim()で前後の空白を削除

        if (newName === '') { //空文字列なら登録しない
            return;
        } else if (newName.length >= 5) {
            return;
        }

        names.push(newName); //配列に名前を追加
        inputName = ''; //入力欄をクリア
    };
    const deleteName = (index: number) => {
        names.splice(index, 1);
    }
    const deleteAllName = () => {
        names = [];
    };
</script>

<h1>名前登録アプリ</h1>

<h2>① 名前を入力</h2>

<input
    type="text"
    placeholder="名前を入力してください"
    value={inputName}
    oninput={(event) => {
        inputName = event.currentTarget.value; //イベントが設定されている入力欄の現在の値です。
    }}
/>
{#if inputName.trim().length >= 5}
    <p style="color: red;">
        名前は4文字以内で入力してください
    </p>
{/if}

<h2>② 入力中の名前</h2>
<p>{inputName}</p>

<button onclick={addName}>登録する</button>
<br>
<button onclick={deleteAllName}>全削除する</button>

<h2>③ 登録済み一覧</h2>

<p>登録件数: {names.length}件</p>

<ul>
    {#each names as name, index}
        <li>
            {index + 1}: {name}
                <button onclick={() => deleteName(index)}>
                    削除する
                </button>
        </li>
    {/each}
</ul>

<a href="/">トップページに戻る</a>