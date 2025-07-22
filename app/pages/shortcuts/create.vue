<template>
  <div class="max-w-4xl mx-auto px-4 py-8">
    <div class="text-center mb-8">
      <h1 class="text-3xl font-bold mb-2">Create New Shortcut</h1>
      <p class="text-gray-600">Build your custom automation workflow</p>
    </div>
    
    <div class="space-y-6">
      <UCard>
        <template #header>
          <h3 class="font-semibold">Basic Information</h3>
        </template>
        <div class="space-y-4">
          <UInput placeholder="Shortcut name" label="Name" required />
          <UTextarea placeholder="Describe your shortcut" label="Description" required />
        </div>
      </UCard>
      
      <UCard>
        <template #header>
          <h3 class="font-semibold">Trigger Configuration</h3>
        </template>
        <div class="space-y-4">
          <USelect placeholder="Select trigger type" label="Trigger Type" required />
          <UInput placeholder="Trigger conditions" label="Trigger Conditions" required />
        </div>
      </UCard>
      
      <UCard>
        <template #header>
          <h3 class="font-semibold">Action Configuration</h3>
        </template>
        <div class="space-y-4">
          <USelect placeholder="Select action type" label="Action Type" required />
          <UTextarea placeholder="Action parameters" label="Action Parameters" required />
        </div>
      </UCard>
      
      <div class="flex gap-4 justify-end">
        <UButton to "/shortcuts" variant="outline">Cancel</UButton>
        <UButton color="primary">Create Shortcut</UButton>
      </div>
    </div>
  </div>
</template>
