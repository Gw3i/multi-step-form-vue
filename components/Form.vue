<template>
  <div class="d-flex flex-column align-items-center gap-5 p-3">
    <h1>Multi Step Form</h1>
    <div class="modal-dialog mw-100">
      <form class="modal-content rounded-4 shadow">
        <fieldset class="modal-body rounded-4 shadow p-5" v-if="step === 1">
          <h2>Job Creation - Hosts</h2>
          <label for="source">
            Select source
            <select name="source" id="source">
              <option>192.168.50.10</option>
              <option>192.168.50.20</option>
              <option>192.168.50.30</option>
              <option>192.168.50.40</option>
              <option>192.168.50.50</option>
            </select>
          </label>
          <label for="snapshots">
            <input id="snapshots" name="snapshots" type="number" />
          </label>
          <label for="sourceSnapshotPath">
            <input
              id="sourceSnapshotPath"
              name="sourceSnapshotPath"
              type="text"
            />
          </label>
          <label for="sourceVolumesPath">
            <input
              id="sourceVolumesPath"
              name="sourceVolumesPath"
              type="text"
            />
          </label>
          <fieldset class="targets">
            <label for="targets">
              Select targets
              <select name="targets" id="targets">
                <option>192.168.50.10</option>
                <option>192.168.50.20</option>
                <option>192.168.50.30</option>
                <option>192.168.50.40</option>
                <option>192.168.50.50</option>
              </select>
            </label>
            <label for="targetSnapshots">
              <input
                id="targetSnapshots"
                name="targetSnapshots"
                type="number"
              />
            </label>
            <label for="priority">
              <input id="priority" name="priority" type="number" />
            </label>
            <label for="targetDirectory">
              <input id="targetDirectory" name="targetDirectory" type="text" />
            </label>
          </fieldset>
          <button type="button" class="btn btn-secondary">+</button>
          <button @click.prevent="step++" class="continueForm btn btn-dark">
            Continue
          </button>
        </fieldset>

        <fieldset class="modal-body rounded-4 shadow p-5" v-if="step === 2">
          <h2>Job Creation - VM</h2>
          <label for="vm">
            Select targets
            <select name="vm" id="vm">
              <option>dedivmts_vm</option>
              <option>dedivmts_vm2</option>
              <option>dedivmts_vm3</option>
              <option>dedivmts_vm4</option>
              <option>dedivmts_vm5</option>
            </select>
          </label>
          <label for="drPostfix"
            >DR Postfix
            <input id="drPostfix" name="drPostfix" type="checkbox" />
          </label>
          <label for="cloneUUID"
            >Clone UUID
            <input id="cloneUUID" name="cloneUUID" type="checkbox" />
          </label>
          <button @click.prevent="step++" class="continueForm btn btn-dark">
            Continue
          </button>
        </fieldset>

        <fieldset class="modal-body rounded-4 shadow p-5" v-if="step === 3">
          <h2>Job Creation - Times</h2>
          <div>
            <label for="interval">
              <input
                type="radio"
                id="interval"
                name="times"
                value="interval"
                checked
              />
              Interval</label
            >
            <label for="timeSlots">
              <input
                type="radio"
                id="timeSlots"
                name="times"
                value="timeSlots"
              />
              TimeSlots</label
            >
          </div>
          <fieldset class="interval bg-light">
            <fieldset v-for="day in days">
              <label for="timesDay"
                >{{ day }}
                <input id="timesDay" name="timesDay" type="checkbox" />
                <label>
                  <select name="" id="">
                    <option value="30min">30min</option>
                    <option value="1h">1h</option>
                    <option value="3h">3h</option>
                    <option value="10h">10h</option>
                    <option value="16h">16h</option>
                  </select>
                </label>
              </label>
              <label for="breakRuleFrom">
                <input id="breakRuleFrom" name="breakRuleFrom" type="time" />
              </label>
              <span>-</span>
              <label for="breakRuleTo">
                <input id="breakRuleTo" name="breakRuleTo" type="time" />
              </label>
            </fieldset>

            <button @click.prevent="step++" class="continueForm btn btn-dark">
              Continue
            </button>
          </fieldset>
        </fieldset>

        <fieldset class="modal-body rounded-4 shadow p-5" v-if="step === 4">
          <h2>Job Creation - Summary</h2>
          <p>Here is the summary</p>
          <button class="continueForm btn btn-dark">Create</button>
        </fieldset>
      </form>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
const days = [
  'Monday',
  'Tuesday',
  'Wednesday',
  'Thursday',
  'Friday',
  'Saturday',
  'Sundays',
]
const step = ref(1)
</script>

<style>
.targets {
  background-color: lightgrey;
}
</style>
