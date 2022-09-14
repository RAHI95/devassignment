<template>
    <div>
      <div class="d-grid gap-2">
        <button
          type="button"
          class="btn btn-success mt-3"
          style="height: auto"
          data-bs-toggle="collapse"
          data-bs-target="#collapse-b1"
          aria-expanded="false"
          aria-controls="collapse-b1"
        >
        <i class="bi bi-arrow-down"></i>
          User
        </button>
      </div>
  
      <div class="d-grid gap-2">
        <button
          type="button"
          class="btn btn-primary mt-1"
          style="height: auto"
          data-bs-toggle="collapse"
          data-bs-target="#collapse-b2"
          aria-expanded="false"
          aria-controls="collapse-b2"
        >
          View
        </button>
      </div>
  
      <div id="myGroup">
        <!-- Add the parent id here -->
  
        <div class="collapse" id="collapse-b1" data-bs-parent="#myGroup">
          <div class="alert alert-success mt-3">User Content</div>
        </div>
  
        <div class="collapse" id="collapse-b2" data-bs-parent="#myGroup">
          <div class="alert alert-primary mt-3">View Content</div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {};
  </script>
  
  <style>
  </style>