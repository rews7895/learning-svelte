<script>
  const fruits = ['apple', 'mango', 'banana', 'grape'];
  const colors = ['red', 'green', 'blue', 'yellow'];
  const person = {
    color: 'yellow',
    name: 'Mark',
    spouse: {
      color: 'blue',
      name: 'Tami'
    }
  };

  const people = [
    {
      id: 1,
      name: 'junseok',
      age: 31
    },
    {
      id: 2,
      name: 'taeyeon',
      age: 33
    }
  ];
</script>

<div class="component-split">
  <h2>Each</h2>
  {#each fruits as fruit}
    <div>{fruit}</div>
  {/each}

  {#each colors as color}
    <div style="color: {color}">{color}</div>
  {/each}

  {#each colors as color, index}
    <div>{index + 1} {color}</div>
  {/each}

  {#each Object.entries(person) as [key, value]}
    <div>found key "{key}" with value {JSON.stringify(value)}</div>
  {/each}
  <!-- 배열에 항목을 추가하거나 삭제하거나, 수정하면 각 항목에 반드시 고유한 식별자를 지정해야 한다. -->
  <!-- 키를 지정하면 스벨트가 DOM 업데이트를 최적화할 수 있다. -->
  {#each people as person (person.id)}
    <div>{person.name} is {person.age} years old.</div>
  {/each}
  <!-- 배열의 모든 요소가 아닌 주어진 횟수만큼 반복문을 실행시키고 싶을 때 -->
  {#each Array(people) as _, index}
    <div>line #{index + 1}</div>
  {/each}
</div>
