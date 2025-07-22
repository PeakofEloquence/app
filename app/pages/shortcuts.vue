<template>
  <div class="max-w-7xl mx-auto px-4 py-8">
    <div class="text-center mb-8">
      <h1 class="text-3xl font-bold mb-2">Shortcuts</h1>
      <p class="text-gray-600">Manage your custom shortcuts and automations</p>
    </div>

    <div class="grid gap-4 mb-8">
      <UCard v-for="shortcut in shortcuts" :key="shortcut.id">
        <template #header>
          <div class="flex items-center justify-between">
            <h3 class="font-semibold">{{ shortcut.name }}</h3>
            <UBadge :color="shortcut.enabled ? 'green' : 'gray'">
              {{ shortcut.enabled ? 'Active' : 'Inactive' }}
            </UBadge>
          </div>
        </template>

        <p class="text-gray-600 mb-4">{{ shortcut.description }}</p>

        <template #footer>
          <div class="flex gap-2">
            <UButton size="sm" @click="editShortcut(shortcut)" variant="outline">
              Edit
            </UButton>
            <UButton size="sm" @click="toggleShortcut(shortcut)" variant="outline">
              {{ shortcut.enabled ? 'Disable' : 'Enable' }}
            </UButton>
            <UButton size="sm" @click="deleteShortcut(shortcut)" color="red" variant="outline">
              Delete
            </UButton>
          </div>
        </template>
      </UCard>
    </div>

    <div class="text-center">
      <UButton to="/shortcuts/create" trailing-icon="i-lucide-plus">
        Create New Shortcut
      </UButton>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

// Mock data for now - will be replaced with actual API calls
const shortcuts = ref([
  {
    id: 1,
    name: 'Auto Email Response',
    description: 'Automatically respond to common support emails',
    enabled: true,
    trigger: 'email_received',
    action: 'send_template_response'
  },
  {
    id: 2,
    name: 'Daily Report Generator',
    description: 'Generate and send daily analytics reports',
    enabled: true,
    trigger: 'time_9am',
    action: 'generate_daily_report'
  },
  {
    id: 3,
    name: 'Slack Bot Integration',
    description: 'Post automated updates to team Slack channel',
    enabled: false,
    trigger: 'project_completed',
    action: 'slack_notification'
  }
])

const editShortcut = (shortcut) => {
  // Navigate to edit page
  navigateTo(`/shortcuts/edit/${shortcut.id}`)
}

const toggleShortcut = (shortcut) => {
  shortcut.enabled = !shortcut.enabled
  // Will need API integration
}

const deleteShortcut = (shortcut) => {
  shortcuts.value = shortcuts.value.filter(s => s.id !== shortcut.id)
  // Will need API integration
}
</script>
