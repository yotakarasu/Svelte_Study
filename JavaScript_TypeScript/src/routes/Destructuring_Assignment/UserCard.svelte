<!-- 子コンポーネント -->
<script lang="ts">
    type Props = {
        name: string;
        age: number;
    };

    let { name, age }: Props = $props(); //$props()は親コンポーネントから渡された値を受け取るための仕組み
</script>

<p>名前: {name}</p>
<p>年齢: {age}</p>