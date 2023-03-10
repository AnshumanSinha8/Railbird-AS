<div class="horizontal-bar-footer" id="footer">
  <span>&copy; Railbird Technologies Inc.</span>
  <script>
    const headerHeight = document.getElementById('header').clientHeight;
    const footer = document.getElementById('footer');
    footer.style.height = `${headerHeight}px`;
  </script>
</div>
  
<style>
  .horizontal-bar-footer {
    background: white;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-top-right-radius: 24px;
    border-top-left-radius: 24px;
    border: 2px solid black;
    margin-top: 7.65px;
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    width: 100%;
  }
  .horizontal-bar-footer span {
    text-align: center;
    width: 100%;
  }
</style>
