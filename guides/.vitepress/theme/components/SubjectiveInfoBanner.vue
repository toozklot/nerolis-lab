<template>
  <div class="subjective-info-banner" role="note">
    <span class="subjective-label">Warning: subjective</span>
    <p class="subjective-text">The information below is advice, and is not necessarily objective information</p>
  </div>
</template>

<style scoped>
.subjective-info-banner {
  margin: 1rem 0;
  padding: 12px 16px;
  border-radius: 8px;
  border: 1px solid color-mix(in oklab, var(--color-primary-500) 45%, transparent);
  background: color-mix(in oklab, var(--color-primary-500) 12%, transparent);
  font-family: var(--font-family-base);
}

.subjective-label {
  display: inline-block;
  margin-bottom: 6px;
  font-size: var(--text-small-size);
  font-weight: var(--font-weight-semibold);
  letter-spacing: var(--tracking-subskill);
  text-transform: uppercase;
  color: var(--color-primary-500);
}

.subjective-text {
  margin: 0;
  font-size: var(--text-body-size);
  font-weight: var(--text-body-weight);
  letter-spacing: var(--tracking-tight);
  line-height: var(--text-body-line-height);
  color: var(--color-neutral-200);
}
</style>
