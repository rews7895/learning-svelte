<script>
  import {tick} from 'svelte';
	// 컴포넌트의 상태 변화를 만듭니다.
	await tick(); // 이 전의 상태 변화가 DOM에 실제로 적용될 때까지 기다립니다.
	// DOM이 업데이트 된 후 추가로 상태를 변화시킵니다.
</script>
