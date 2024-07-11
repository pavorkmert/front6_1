<script>
  export let title;
  export let description;
</script>

<div class="project-card">
  <h5>{title}</h5>
  <p>{description}</p>
</div>

<style>
.project-card {
  flex: 1;
  padding: 20px;
  background-color: #e9ecef;
  border-radius: 10px;
  text-align: center;
}
.project-card h5 {
  font-size: 1.25em;
  margin-bottom: 10px;
}
.project-card p {
  font-size: 1em;
  color: #6c757d;
}
</style>
