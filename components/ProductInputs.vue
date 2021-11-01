<template>
  <div class="flex justify-start space-x-2 w-full">
    <div class="flex flex-col items-start space-y-1 flex-grow-0">
      <label class="text-gray-500 text-base">
        Qty.
      </label>
      <input
        type="number"
        inputmode="numeric"
        id="quantity"
        name="quantity"
        min="1"
        step="1"
        class="text-gray-900 form-input border border-gray-300 w-16 rounded-sm focus:border-palette-light focus:ring-palette-light"
        value="1"
      >
    </div>
    <div class="flex flex-col items-start space-y-1 flex-grow">
      <label class="text-gray-500 text-base">
        Size
      </label>
      <select
        id="size-selector"
        name="size-selector"
        class="form-select border border-gray-300 rounded-sm w-full text-gray-900 focus:border-palette-light focus:ring-palette-light"
      >
        <option
          id="Z2lkOi8vc2hvcGlmeS9Qcm9kdWN0VmFyaWFudC8zNjIyNDIzNDA5NDc0Nw=="
          value="Z2lkOi8vc2hvcGlmeS9Qcm9kdWN0VmFyaWFudC8zNjIyNDIzNDA5NDc0Nw=="
        >
          3 x 3
        </option>
        <option
          id="Z2lkOi8vc2hvcGlmeS9Qcm9kdWN0VmFyaWFudC8zNjIyNDIzNDEyNzUxNQ=="
          value="Z2lkOi8vc2hvcGlmeS9Qcm9kdWN0VmFyaWFudC8zNjIyNDIzNDEyNzUxNQ=="
        >
          4 x 4
        </option>
        <option
          id="Z2lkOi8vc2hvcGlmeS9Qcm9kdWN0VmFyaWFudC8zNjIyNDIzNDE2MDI4Mw=="
          value="Z2lkOi8vc2hvcGlmeS9Qcm9kdWN0VmFyaWFudC8zNjIyNDIzNDE2MDI4Mw=="
        >
          5.5 x 5.5
        </option>
      </select>
    </div>
  </div>
</template>

<style scoped>
  .form-input, .form-select {
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
    background-color: #fff;
    border-color: #6b7280;
    border-width: 1px;
    border-radius: 0;
    padding: .5rem .75rem;
    font-size: 1rem;
    line-height: 1.5rem;
  }

  .form-select {
    background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' fill='none' viewBox='0 0 20 20'%3e%3cpath stroke='%236b7280' stroke-linecap='round' stroke-linejoin='round' stroke-width='1.5' d='M6 8l4 4 4-4'/%3e%3c/svg%3e");
    background-position: right .5rem center;
    background-repeat: no-repeat;
    background-size: 1.5em 1.5em;
    padding-right: 2.5rem;
    -webkit-print-color-adjust: exact;
    color-adjust: exact;
  }
</style>
