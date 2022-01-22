<template>
  <div class="navbar mb-2 shadow-lg bg-neutral text-neutral-content">
    <div class="flex-none px-2 mx-2">
      <span class="text-lg font-bold">
        Hacker Nuews
      </span>
    </div>
    <div class="flex-1 px-2 mx-2">
      <div class="items-stretch hidden lg:flex">
        <a class="btn btn-ghost btn-sm rounded-btn">
          Top
        </a>
        <a class="btn btn-ghost btn-sm rounded-btn">
          New
        </a>
        <a class="btn btn-ghost btn-sm rounded-btn">
          Show
        </a>
        <a class="btn btn-ghost btn-sm rounded-btn">
          Ask
        </a>
        <a class="btn btn-ghost btn-sm rounded-btn">
          Jobs
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'NavBar'
}
</script>
