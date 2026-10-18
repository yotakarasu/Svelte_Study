<script lang="ts">
    type Props = {
        names: string[];
    }; // 親コンポ―ネントから受け取るプロパティ(Props)の型を定義するもの Props : 定義した型の名前(任意の名前に変更可能)

    // 親から配列を受け取る
    let { names }: Props = $props();

    // 配列の分割代入
    let [name1, name2, name3] = $derived(names); // $derived()はリアクティブな値（$state や $props など）が変更されると自動的に再計算する仕組み
</script>


<p>{name1}</p>
<p>{name2}</p>
<p>{name3}</p>
