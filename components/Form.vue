<template>
  <div class="d-flex flex-column align-items-center gap-5 p-3">
    <h1>Multi Step Form</h1>
    <form>
      <fieldset id="1">
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
          <input id="sourceVolumesPath" name="sourceVolumesPath" type="text" />
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
            <input id="targetSnapshots" name="targetSnapshots" type="number" />
          </label>
          <label for="priority">
            <input id="priority" name="priority" type="number" />
          </label>
          <label for="targetDirectory">
            <input id="targetDirectory" name="targetDirectory" type="text" />
          </label>
        </fieldset>
        <button type="button" class="btn btn-secondary">+</button>
        <button class="continueForm btn btn-dark">Continue</button>
      </fieldset>

      <fieldset id="2">
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
          <label for="drPostfix">DR Postfix
            <input id="drPostfix" name="drPostfix" type="checkbox">
          </label>
          <label for="cloneUUID">Clone UUID
            <input id="cloneUUID" name="cloneUUID" type="checkbox">
          </label>
          <button class="continueForm btn btn-dark">Continue</button>
      </fieldset>

      <fieldset id="3">
        <h2>Fieldset 3</h2>
      </fieldset>

      <fieldset id="4">
        <h2>Fieldset 4</h2>
      </fieldset>
    </form>
  </div>
</template>

<script setup>
function hello() {
  alert('Hello')
}
</script>

<style>
.targets {
  background-color: lightgrey;
}
</style>
