<script>
  import { Stack } from "$lib/components/atoms/index";

  export let title;
  export let description;
  export let background = false;
  export let center = false;
</script>

<div class:with-background={background} class:center class="main-wrapper">
  <div class="row" class:column={center}>
    <slot />
    <h4>
      {title}
    </h4>
  </div>
  <p>
    {@html description}
  </p>
</div>

<style type="scss">
  .main-wrapper {
    margin-bottom: 2.4rem;
  }
  .row {
    display: flex;
    flex-direction: row;
    justify-content: left;
    align-items: center;
    gap: 0.6rem;
  }
  .column {
    flex-direction: column;
    gap: 1rem;
  }
  h4 {
    font-size: var(--fs-400);
    font-weight: 900;
    letter-spacing: 0.05rem;
    color: var(--clr-primary-main);
  }
  p {
    font-size: var(--fs-300);
    margin-top: 1em;
    color: var(--clr-font-text-soft);
    max-width: 43ch;
  }

  .with-background {
    border-radius: 1rem;
    background-color: var(--clr-primary-main-t9);
    padding: 1.6rem;
    border: 3px var(--clr-primary-main-t8) solid;
  }

  .center {
    text-align: center;
  }
</style>
