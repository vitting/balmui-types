<template>
  <div>
    <ui-top-app-bar content-selector="#main" nav-icon="false">
      Fieldtypes
    </ui-top-app-bar>
    <main id="main">
      <div class="buttons">
        <ui-button raised @click="type = 0">Flat</ui-button>
        <ui-button raised @click="type = 1">Outlined</ui-button>
        <ui-button raised @click="convert">Convert</ui-button>
      </div>
      <hr>
      <div>
        <h4>Titel</h4>
      </div>
      <hr>
      <div>
        <ui-form-field>
          <ui-checkbox></ui-checkbox>
          <label v-tooltip="'plain tips'">Checkbox</label>
          <ui-icon
            :class="$theme.getThemeClass('primary')"
            class="tooltip"
            v-tooltip="'plain tips'"
            aria-describedby="tooltip-id"
          >
            info
          </ui-icon>
        </ui-form-field>
      </div>
      <hr>
      <div>
        <ui-form-field>
          <ui-select
            :type="type"
            id="full-func-js-select"
            :options="[
              { label: 'Ingen hat', value: '-1' },
              { label: 'Hat 1', value: '0' },
              { label: 'Hat 2', value: '1' },
              { label: 'Hat 3', value: '2' },
              
            ]"
          >
            Vælg en hat
          </ui-select>
          <ui-icon
            class="tooltip"
            v-tooltip="'plain tips'"
            aria-describedby="tooltip-id2"
          >
            info
          </ui-icon>
        </ui-form-field>
      </div>
      <hr>
      <div>
        <ui-datepicker toggle :type="type" label="Oprettelses dato"></ui-datepicker>
      </div>
      <hr>
      <div>
        <ui-textfield
          :required="false"
          helper-text-id="my-text-field-helper-text"
          label="Skriv dit navn"
          :type="type"
        ></ui-textfield>
      </div>
      <hr>
      <div>
        <ui-textfield
          :type="type"
          :required="false"
          helper-text-id="my-text-field-helper-text"
          label="Number Field"
          input-type="number"
        ></ui-textfield>
      </div>
      <hr>
      <div>
        <h4>Chose a choice</h4>
        <ui-form-field>
          <ui-radio v-model="yesno" input-id="yes" value="y"></ui-radio>
          <label for="yes">Yes</label>
        </ui-form-field>
        <ui-form-field>
          <ui-radio v-model="yesno" input-id="no" value="n"></ui-radio>
          <label for="no">No</label>
        </ui-form-field>
      </div>
      <hr>
      <div class="option-list">
        <ui-form-field>
          <ui-radio v-model="radiolist" input-id="choice1" value="1"></ui-radio>
          <label for="choice1">Choice 1</label>
        </ui-form-field>
        <ui-form-field>
          <ui-radio v-model="radiolist" input-id="choice2" value="2"></ui-radio>
          <label for="choice2">Choice 2</label>
        </ui-form-field>
        <ui-form-field>
          <ui-radio v-model="radiolist" input-id="choice3" value="3"></ui-radio>
          <label for="choice3">Choice 3</label>
        </ui-form-field>
        <ui-form-field>
          <ui-radio v-model="radiolist" input-id="choice4" value="4"></ui-radio>
          <label for="choice4">Choice 4</label>
        </ui-form-field>
      </div>
      <hr>
      <div>
        <ui-textfield
          :type="type"
          required
          input-type="textarea"
          rows="8"
          cols="40"
          label="Textarea"
        ></ui-textfield>
      </div>
      <hr>
      <div class="hyperlink">
        <a href="/">dr.dk</a>
        <ui-textfield-icon>link</ui-textfield-icon>
        
      </div>
    </main>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'App',

  components: {},
  data() {
    return {
      yesno: '',
      radiolist: '',
      type: 1,
      what: {
        test1: "34",
        tester() {
          let a = 2;
          console.log(a)
        }
      }
    }
  },
  methods: {
    convert() {
      console.log(this.what);
      console.log(JSON.stringify(this.what));
    }
  }
})
</script>

<style scoped>
#main > div {
  padding: 1rem;
}
.buttons > * {
  margin-right: 10px;
}
.option-list {
  display: flex;
  flex-direction: column;
}

.tooltip {
  margin-left: 10px;
}

.hyperlink {
  display: flex;
  justify-items: center;
}

.hyperlink a {
  text-decoration: none;
}
</style>
