<script>
  export let color = 'blue';
  let hhmmss = '';
  setInterval(() => {
    hhmmss = new Date().toLocaleTimeString();
  }, 1000);
</script>

<div class="component-split">
  <span style="color: {color}">{hhmmss}</span>
</div>
