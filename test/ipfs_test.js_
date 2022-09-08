const CID = require('cids')
describe("test", function () {
  function getValidHttpUrl(data) {
    let url;
    try {
      url = new URL(data);
    } catch (_) {
      const cid = new CID(data);
      // ipfs hash : Qm...
      return process.env.IPFS_BASEURL + data;
    }
    if (url.protocol === "http:" || url.protocol === "https:") return data;
    if (url.protocol === "ipfs:") {
      return "https://nftstorage.link/ipfs/" + url.hostname + url.pathname;
    }
    throw new Error("invalid");
  }

  it("check valid url", async function () {
    const httpUrl = "https://github.com/loganworld/ICICB-Marketplace-frontend/blob/main/src/components/pages/explore.js";
    const ipfsUrl = "ipfs://bafybeic572uupzxkkdefttaybsjq2xqn5dcngbdpdh3tla6mbzrlpw63tq/1";
    const ipfsHash = "QmShtKZfFZfQPiVoh3DBipgrYes21VpKckmePe8iA1nnjB";
    console.log(getValidHttpUrl(httpUrl));
    console.log(getValidHttpUrl(ipfsUrl));
    console.log(getValidHttpUrl(ipfsHash));
  });
});