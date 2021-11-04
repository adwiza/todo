<<template>
  <div>
    <h1>Todos</h1>
    <p>{{ msg }}</p>
  <table>
      <thead>
  <tr>
      <th>Uid</th>
      <th>Описание</th>
      <th>Выполнена?</th>
  </tr>
  </thead>
  <tbody>
    <tr v-for="(todo, index) in todos" :key="index">
    <td>{{ todo.uid }}</td>
    <td>{{ todo.description }}</td>
    <td>
    <span v-if="todo.is_completed">Выполнено</span>
    <span v-else>Не выполнено</span>
    </td>
    </tr>
  </tbody>
  </table>
  </div>
</template>
<script>
import axios from 'axios';

const dataURL = 'http://localhost:5000/api/tasks/';

export default {
  name: 'Fetch',
  data() {
    return {
      msg: 'Запрос ещё не прошёл',
    };
  },
  methods: {
    getMessage() {
      axios.get(dataURL)
        .then((response) => {
          console.table(response.data.tasks);
          // this.msg = response.data.message;
        });
    },
  },
  created() {
    this.getMessage();
  },
};
</script>
