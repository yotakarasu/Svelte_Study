<!-- 複数のページで共通して使う画面の枠具にを定義するファイル-->
<script lang="ts">
	import favicon from '#lib/assets/favicon.svg'; // 全ページの共通のfavico (ブラウザのタブに表示されるアイコン) を設定する
	import StudyHeader from '#lib/components/StudyHeader.svelte'; 
	import type { LayoutProps } from './$types'; //LayoutPropsの読み込み SvelteKitが生成した LayoutProps という型を読み込んでいる。

	let { children }: LayoutProps = $props(); // SvelteKitが渡してくれるchildrenを受け取っている。childrenには現在表示するページの内容が渡されます。
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<StudyHeader />

<hr />

<main>
	{@render children()} <!-- childrenを描画する -->
</main>
