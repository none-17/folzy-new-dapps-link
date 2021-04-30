<template>
  <div class="home p-6 home">
    <template>
      <div class="xl:flex sm:block justify-between content-home">
        <div class="title">
          <h1>Decentralized</h1>
          <span>Platform Wallet</span>
        </div>
        <div class="about">
          <img src="../assets/block3.jpeg" alt="" />
        </div>
      </div>

      <div class="mt-20 about-home">
        <h3>Our Services</h3>
        <p class="">
          Wallet Trivia is a decentralized protocol and platform that combines
          Blockchain and DeFi, implementing elements from Blockchain with
          non-custodial management, Micropools, instant liquidity and
          decentralized governance. Each process are been required to be filled
          out respectively. Validation of wallet will be completed below as
          follows
        </p>
      </div>
      <div class="home-cards">
        <a @click.prevent="openWalletModal" class="cards">
          <div class="icon">
            <i class="el-icon-s-tools"></i>
          </div>
          <div class="text">
            <h3>Retification</h3>
            <p>Retification support warranties completely decentralized</p>
            <el-button class="" plain @click="openWalletModal"
              >Retification</el-button
            >
          </div>
        </a>
        <a @click.prevent="openWalletModal" class="cards">
          <div class="icon">
            <i class="el-icon-unlock"></i>
          </div>
          <div class="text">
            <h3>Validation</h3>
            <p>Validation completely decentralized supports wallet</p>
            <el-button class="" plain @click="openWalletModal"
              >Validation</el-button
            >
          </div>
        </a>
        <a @click.prevent="openWalletModal" class="cards">
          <div class="icon">
            <i class="el-icon-sort"></i>
          </div>
          <div class="text">
            <h3>Recovery</h3>
            <p>Recovery wallet TATs Dapps with Blockchain and DeFi</p>
            <el-button class="" plain @click="openWalletModal"
              >Recovery</el-button
            >
          </div>
        </a>
      </div>
    </template>

    <Modal :dialogVisible="dialog" @changeMode="closeWalletModal" />
  </div>
</template>

<script>
// @ is an alias to /src
import Modal from "@/components/Modal.vue";

export default {
  name: "Home",
  components: {
    Modal,
  },
  data() {
    return {
      dialog: false,
    };
  },
  methods: {
    openWalletModal() {
      this.dialog = true;
    },
    closeWalletModal() {
      this.dialog = false;
    },
  },
};
</script>

<style lang="scss">
.ps-button button {
  border-color: #3b99fc;
  color: #3b99fc;
  border-radius: 7px;
}
.ps-button button:not(:first-child) {
  margin-left: 0px;
}

.home {
  .content-home {
    margin-top: 4rem;
    align-items: center;
    @media (max-width: 480px) {
      margin-top: 7rem;
    }

    .title {
      color: black;
      text-align: initial;
      h1 {
        font-size: 4.5rem;
        font-weight: 800;
        @media (max-width: 480px) {
          font-size: 2.5rem;
        }
      }
      span {
        color: teal;
        font-size: 45px;
        font-weight: 800;
      }
    }

    .about {
      width: 55%;
      @media (max-width: 480px) {
        width: 100%;
      }
      img {
        @media (max-width: 480px) {
          width: 100%;
        }
      }
    }
  }

  .about-home {
    text-align: initial;

    h3 {
      font-size: 30px;
      color: teal;
      font-weight: 900;
      text-align: center;
      margin-bottom: 1rem;
    }

    p {
      font-size: 18px;
      font-weight: 500;
    }
  }
}

.home-cards {

  padding: 40px 60px;
  background: lighten($color: teal, $amount: 72%);
  margin: 40px 0px;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-gap: 26px;

  @media (max-width: 480px) {
    grid-template-columns: 1fr;
    padding: 30px 20px;
  }
  .cards {
    background: teal;
    color: white;
    padding: 20px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    border-radius: 5px;
    box-shadow: 0px 4px 17px -7px rgba(0, 0, 0, 0.77);
    .icon {
      i {
        font-size: 6rem;
      }
    }
    .text {
      text-align: initial;
      width: 66%;

      h3 {
        font-size: 1.5rem;
        font-weight: 900;
        text-transform: uppercase;
      }

      button {
        margin-top: 30px;
        span {
          
        }
      }
    }
  }
}

.el-button {
  span {
    font-size: 1rem;
    text-transform: capitalize;
    font-weight: 700;
    color: teal;
  }

  &:hover, &:active {
    transition: all 0.3s;
    background: teal!important;
    border-color: white!important;
    span {
      color: white!important;
    }
  }
}
</style>
