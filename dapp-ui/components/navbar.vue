<template>
  <div>
    <nav class="navbar navbar-expand-lg navbar-light fixed-top">
      <ul class="navbar-nav justify-content-end ml-auto">
        <li class="nav-item">
          <b-button v-on:click="toggle" class="mr-5 mt-3">
            <span>Rent Your Property</span>
          </b-button>
        </li>
      </ul>
    </nav>

    <property-form v-if="showModal">
      <h3 slot="header">Rent Your Property</h3>
    </property-form>
  </div>
  <li class="nav-item">
  <b-button v-on:click="walletConnect" class="mr-5 mt-3">
    <span>WalletConnect</span>
  </b-button>
</li>
<b-button v-on:click="sendTx" class="mr-5 mt-3">
  <span>Send Transaction</span>
</b-button>
</template>

<script>
import PropertyForm from "~/components/propertyForm.vue";
import { accountAddress, setProvider, web3 } from "~/plugins/utils";
import { initWalletConnect } from "~/plugins/walletConnect";

export default {
  data() {
    return {
      showModal: false,
      address: null
    };
  },
  components: {
    PropertyForm
  },
  methods: {
    toggle() {
      this.showModal = !this.showModal;
    },
    walletConnect() {
      // TODO: connect to walletconnect
      initWalletConnect();
    }
  }
};
</script>
