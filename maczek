 intid = setInterval(() => {
      getPrize(
        mcd.bridge.message("offerActivation"),
        parseInt(document.querySelector(".loyalityId").value)
      );
      if (document.querySelector(".catboy").checked) {
        document.querySelector(".loyalityId").value =
          parseInt(document.querySelector(".loyalityId").value) - 1;
      }
    }, 1500);
  });
  document
    .querySelector(".napierdalacz-stop")
    .addEventListener("click", () => {
      if (intid) clearInterval(intid);
    });
  document.addEventListener("mcdBridgeReady", function (e) {
    console.log(mcd);
    let offerActivation = mcd.bridge.message("offerActivation");
    let user = mcd.bridge.message("user");
    user.send({ promptlogin: true });
    user.on("data", function (data) {
      console.log(JSON.stringify(data));
      //   getPrize(offerActivation);
      let i = 985;
    });
    user.on("error", function (error) {});
    user.on("done", function () {});
  });
  function getPrize(offerActivation, loyalityId) {
    let couponId =
      coupons[Math.floor(Math.random() * coupons.length) + 1 - 1];

    offerActivation.send({
         loyaltyId: 2400,
          autoActivate: false,
          rewardId: 00001
    });
    offerActivation.on("data", function (data) {
      console.log("offer activation data", loyalityId, data);
    });
    offerActivation.on("error", function (error) {
      console.warn("MCD ERROR", loyalityId, JSON.stringify(error));
    });
    offerActivation.on("done", function () {
      console.log("corn done", loyalityId);
    });
  }
</script>
<script src="//cdn.jsdelivr.net/npm/eruda"></script>
<script>
  eruda.init();
