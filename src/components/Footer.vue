<template>
  <div id="footer">
      <h1>Get <span>in Touch</span></h1>
      <p>So that we can talk more about...</p>
      <div class="contactId">
        <i class="fa-solid fa-envelope"></i>
        <i class="fa-brands fa-behance"></i>
        <i class="fa-brands fa-dribbble"></i>
        <i class="fa-brands fa-linkedin-in"></i>
      </div>
  </div>
</template>

<script>
export default {
    
}
</script>

<style scoped>
#footer {
    margin-block: 80px;
}

    p {
        font-size: 18px;
        font-weight: 100;
    }
    .contactId {
        display: flex;
        align-items: center;
        justify-content: center;
        margin-top: 60px;
        gap: 56px;
    }
    .contactId i {
        font-size: 42px;
        transition: transform 0.3s ease;
    }
    .contactId i:hover {
        transform: scale(1.1);
        cursor: pointer;
    }

    @media (max-width: 900px) {
        h1 {
            font-size: 35px;
        }
        .contactId {
            gap: 40px;
            margin-top: 40px;
        }
        .contactId i {
            font-size: 28px;
        }
    }
</style>