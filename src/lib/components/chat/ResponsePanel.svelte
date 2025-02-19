<script>
  import Badge from '../common/Badge.svelte';

  export let response = {
    tags: [],
    confidence: 0,
    analysis: '',
    dissent: '',
    needs_iteration: false,
    refinement_areas: ''
  };
</script>

<div class="response-panel">
  <div class="tags">
    <h3>Tags</h3>
    <ul>
      {#each response.tags as tag}
        <li>
          <Badge type="info" content={tag} />
        </li>
      {/each}
    </ul>
    <p>Confidence: {response.confidence}</p>
  </div>

  <div class="analysis">
    <h3>Analysis</h3>
    <p>{response.analysis}</p>
  </div>

  <div class="dissent">
    <h3>Dissent</h3>
    <p>{response.dissent}</p>
  </div>

  <div class="iteration-status">
    <h3>Iteration Status</h3>
    <p>Needs Iteration: {response.needs_iteration ? 'Yes' : 'No'}</p>
    {#if response.needs_iteration}
      <p>Refinement Areas: {response.refinement_areas}</p>
    {/if}
  </div>
</div>
