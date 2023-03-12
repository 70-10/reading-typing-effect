<script lang="ts">
  import Typewriter from "svelte-typewriter";

  let displayText = "";
  let text =
    "ここに文章を入力して送信ボタンを押すと、下にタイピングエフェクトで出力されます。";

  function handleOnSubmit() {
    const tmp = text.slice();
    displayText = tmp;
  }
</script>

<section>
  <textarea
    class="my-2 resize shadow appearance-none border rounded h-80 w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
    bind:value={text}
  />

  <button
    on:click={handleOnSubmit}
    class="my-2 rounded border py-2 px-3 bg-green-500 text-white hover:bg-green-600"
    >送信</button
  >
</section>

<hr class="my-5" />

<section>
  <Typewriter
    mode="cascade"
    interval={80}
    delay={100}
    keepCursorOnFinish={500}
    showCursorOnDelay={true}
  >
    <p class="text-xl">{displayText}</p>
  </Typewriter>
</section>
