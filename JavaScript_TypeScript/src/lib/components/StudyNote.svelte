<script lang="ts">
    type Props = { // type Props : 親から受け取る値の型を定義
        title: string;
        description: string;
    };

    let { title, description }: Props = $props(); //親から渡された値を受け取る
</script>

<div class="study-note">
    <h3>{title}</h3>
    <p>{description}</p>
</div>

<style>
    .study-note {
        padding: 16px;
        background-color: #f0f0f0;
        border-radius: 8px;
        color: #222;
    }
</style>