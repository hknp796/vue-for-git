<template>
  <div>
    <v-app>
      <v-form>
        <v-container>
          <v-row>
            <v-col>
              <v-text-field
                v-model="arraysize"
                label="Enter total socks number"
                type="number"
              >
              </v-text-field>
            </v-col>
          </v-row>
          <v-row>
            <v-col>
              <v-text-field
                v-model="inputarraystring"
                label="Enter colors with space between"
                type="text"
              >
              </v-text-field>
              {{ this.inputarraystring }}
            </v-col>
          </v-row>
          <template>
            <v-btn color="primary" @click="submit">submit</v-btn>
          </template>
          <v-row>
            <br />
            <p v-if="this.input" class="mt-10">
              array size is {{ this.totalpairs }}
            </p>
          </v-row>
        </v-container>
      </v-form>
    </v-app>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arraysize: 0,
      inputarraystring: '',
      inputarray: [],
      input: false,
      totalpairs: 0,
    };
  },
  methods: {
    submit() {
      this.inputarray = this.inputarraystring.split(' ')
      // let unique = [...new Set(this.inputarray)];
      console.log(this.inputarray);
        let unique = this.inputarray.filter()
      const sortedobject = {};
      unique.forEach((x) => {
        sortedobject[x] = (sortedobject[x] || 0) + 1;
      });
      this.totalpairs = 0;
      for (let i = 0; i < unique.length; i++) {
        this.totalpairs = this.totalpairs + sortedobject[unique[i]] / 2;
      }
      this.input = true;
    },
  },
};
</script>
