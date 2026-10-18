
<script lang="ts">
    import UserCard from './UserCard.svelte'; // これでUserCard.svelteを読み込む処理
    import ArrayUserCard from './ArrayUserCard.svelte';
    import StudyNote from '#lib/components/StudyNote.svelte';

    const names = ['からす', 'すずめ', 'はと'];

    const user = {
        name: 'からす',
        age: 28
    };

    const { name, age } = user;
</script>

<h1>分割代入の学習</h1>

<StudyNote
    title="学習メモ"
    description="分割代入は配列やオブジェクトから値を取り出す構文です。"
/>

<h2>① JavaScriptの分割代入</h2>

<p>名前: {name}</p>
<p>年齢: {age}</p>

<h2>② SvelteのPropsと分割代入</h2>

<UserCard name={name} age={age} /> <!--読み込んだコンポーネントを画面に配置しnameとageの値を渡す処理-->

<h2>③ 配列の分割代入</h2>

<ArrayUserCard names={names} />
