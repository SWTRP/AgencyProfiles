<style>
.table {
  display: flex;
  justify-content: center;
}
</style>
<template>
<v-container>
  <v-layout text-center wrap>
    <v-flex xs12>
      <v-img :src="require('../assets/GDOT_logo.png')" class="my-3" contain height="200"></v-img>
    </v-flex>

    <v-flex mb-4>
      <h1 class="display-2 mb-3">
        Please review your agency's profile document </h1> <br>
      <h2>If needed, please reference the instructions page <a href="https://firebasestorage.googleapis.com/v0/b/swtrp-9fda0.appspot.com/o/Instructions.pdf?alt=media&token=5f2e3af9-d4f2-4387-88b4-6cef2f49bfb6" target="_blank"> available here</a></h2>
      <br>
      <p class="subheading font-weight-regular">
        For more information about the SWTRP
        <br>please visit
        <a href="http://www.dot.ga.gov/InvestSmart/Transit/Pages/TransitPlan.aspx" target="_blank">SWTRP's page on GDOT's website</a>
      </p>
    </v-flex>

    <v-flex xs10 offset-xs1 mb-6>
      <!-- <h2 class="headline font-weight-bold mb-3">Documents</h2> -->
      <v-card>
        <v-card-title>
          Profile Documents
          <div class="flex-grow-1"></div>
          <v-text-field v-model="search" append-icon="" label="Search" single-line hide-details></v-text-field>
        </v-card-title>
        <v-data-table
          :headers="headers"
          :items="docs"
          :search="search"
          :items-per-page="15"
          >
          <template v-slot:item.href="{item}">
            <v-btn text small color="primary" v-bind:href="item.href" target="_blank">Link to Document</v-btn>
          </template>
        </v-data-table>
      </v-card>
    </v-flex>
  </v-layout>
</v-container>
</template>

<script>
export default {
  data() {
    return {
      search: '',
      headers: [{
          text: 'Agency',
          align: 'left',
          sortable: true,
          value: 'name',
        },
        {
          text: 'Document',
          value: 'href'

        },
      ],
      docs: [{
          name: 'Albany Transit',
          href: 'https://drive.google.com/open?id=1NHxPWq6VHKZDLVOAQtLJ4yNA-tgy4PuW',
        },
        {
          name: 'Americus Transit',
          href: 'https://drive.google.com/open?id=1AM8qN_nn5ih6f2rGl9nfNsgfRlUSeZYW',
        },
        {
          name: 'Athens Transit System',
          href: 'https://drive.google.com/open?id=1xbB7MY8f6M3kPHmOWV-PhzoQ8YVOZqv0'
        },
        {
          name: 'Augusta Richmond County Transit System',
          href: 'https://drive.google.com/open?id=1yDfd9vuuyQbBnejtXgRao6PEGW5a1d96',
        },
        {
          name: 'Bacon County Transit',
          href: 'https://drive.google.com/file/d/1l7txOaP1zMG7mpSp3eyiY-02cpgQd6FF/view?usp=sharing',
        },
        {
          name: 'Baldwin County Transit',
          href: 'https://drive.google.com/file/d/1KNecb0uLbE3Uqb22DacdKqhD8dmaXO6f/view?usp=sharing',
        },
        {
          name: 'Banks County Transit',
          href: 'https://drive.google.com/file/d/1xOUDcSrMYqgwbYEi2URZmvoKtIkq2LyY/view?usp=sharing',
        },
        {
          name: 'Bartow County Transit',
          href: 'https://drive.google.com/file/d/1_LUWmrCXImLdM9mVQjvBZnGF9PHrOgT8/view?usp=sharing',
        },
        {
          name: 'Ben Hill County Transit Syste',
          href: 'https://drive.google.com/file/d/1ywXW60UtRUuOFcrARqRIhbD_I_YlAe5P/view?usp=sharing',
        },
        {
          name: 'Berrien County Transit',
          href: 'https://drive.google.com/file/d/1zsgTxrBfyFt0ZZ4Qi9PKkl5If65jrQsn/view?usp=sharing',
        },
        {
          name: 'Bleckley County Transit',
          href: 'https://drive.google.com/file/d/1M_oy2PeXuAnpSo0br2Z0gqXc04uMBll8/view?usp=sharing',
        },
        {
          name: 'Brantley County Transit',
          href: 'https://drive.google.com/file/d/18oFxyQwyM_vYi2rCNWVg_LQxAf3l9l_X/view?usp=sharing',
        },
        {
          name: 'Brooks Transit',
          href: 'https://drive.google.com/file/d/1G_yQAN5R-J8rMpLvoCjDCeHw-oZ6QHsl/view?usp=sharing',
        },
        {
          name: 'Burke County Transit',
          href: 'https://drive.google.com/file/d/1tX5sjoFLaTDAKBIJZgvnGAcYlHkiDqgD/view?usp=sharing',
        },
        {
          name: 'Carroll County Connection',
          href: 'https://drive.google.com/file/d/1Lf5MOi9M77_c4-dtYahBm7QepcfWS8pm/view?usp=sharing',
        },
        {
          name: 'Catoosa Trans-Aid',
          href: 'https://drive.google.com/file/d/1vxD6sy4DVLqSgd11rB6hS1rF2jY2koRw/view?usp=sharing',
        },
        {
          name: 'Cedartown Transit',
          href: 'https://drive.google.com/file/d/1wYx_6v-4o3bLYA9v9_Dyup0EOCFkG5SD/view?usp=sharing',
        },
        {
          name: 'Chatham Area Transit',
          href: 'https://drive.google.com/file/d/1-crLytOY7gDDtgpZTFU4Tcfm_AHWQkRu/view?usp=sharing',
        },
        {
          name: 'Chattooga County Transit System',
          href: 'https://drive.google.com/file/d/1WoriWgJBtVSpz-P3Yzf6oLYL8IfjpF-f/view?usp=sharing',
        },
        {
          name: 'Cherokee Area Transportation System',
          href: 'https://drive.google.com/file/d/1-_q8guBQGMjrmKuHreRuKSzTLe9FYPhI/view?usp=sharing',
        },
        {
          name: 'Clay County Transit',
          href: 'https://drive.google.com/file/d/1m9Kgrf955z7KwHzQbV0HeyvzgXaFF-Ce/view?usp=sharing',
        },
        {
          name: 'Coastal Region Commission',
          href: 'https://drive.google.com/file/d/1CL72ktDiheRaIF_gwB0zc9uxoJzGzeXI/view?usp=sharing',
        },
        {
          name: 'CobbLinc',
          href: 'https://drive.google.com/file/d/1ZKWgkJdoeUW1de_YMaf26GNaSRlQ9gcF/view?usp=sharing',
        },
        {
          name: 'Columbia County Public Transit',
          href: 'https://drive.google.com/file/d/1mXEJWMIgZt_cn7jGoDCLD4_1jsGdgUG1/view?usp=sharing',
        },
        {
          name: 'Connect Douglas',
          href: 'https://drive.google.com/file/d/1dWkV6CcEE53OeWj40A0hERjt-JUDrNOn/view?usp=sharing',
        },
        {
          name: 'Cook County Transit System',
          href: 'https://drive.google.com/file/d/1EGyTl46t487ZTvcawkXFpD2r5RTAKUMh/view?usp=sharing',
        },
        {
          name: 'Coweta County Transit',
          href: 'https://drive.google.com/file/d/1xZG02xV8MAvT8IA7AcLRtv_9euPsvuCZ/view?usp=sharing',
        },
        {
          name: 'Crawford County Transportation Authority',
          href: 'https://drive.google.com/file/d/1CkLGxhwL08Iy8E-j5hw59GfLtlTxn05t/view?usp=sharing',
        },
        {
          name: 'Crisp Area Regional Transit',
          href: 'https://drive.google.com/file/d/1V6OAzAV6JNMoDlqfkdxqLxWC70E1DRqi/view?usp=sharing',
        },
        {
          name: 'Dade County Transit',
          href: 'https://drive.google.com/file/d/1OUAxNWyazr1uLssLJyle1cPnI7iQ7z8A/view?usp=sharing',
        },
        {
          name: 'Dawson County Transit',
          href: 'https://drive.google.com/file/d/10cG09HtCRno3ervhwpiijQ0UKBIJH1Xf/view?usp=sharing',
        },
        {
          name: 'Dodge County Transit',
          href: 'https://drive.google.com/file/d/1ja9ZJkvrCZS7OIjQg-wQhpBRMNA-bg93/view?usp=sharing',
        },
        {
          name: 'Dooly County Transit',
          href: 'https://drive.google.com/file/d/1KxMmsmDbwCNo61Lly6v360BQ2h3SlOmD/view?usp=sharing',
        },
        {
          name: 'Elbert Transit',
          href: 'https://drive.google.com/file/d/1_dHMMZT5OFp3IlUAUJ36MRMeRPEf-R-G/view?usp=sharing',
        },
        {
          name: 'Forsyth County Dial-A-Ride',
          href: 'https://drive.google.com/file/d/1Jfyw3i5UkQrFi1JBXu_FTVmusfjYHBz1/view?usp=sharing',
        },
        {
          name: 'Glascock County Transit',
          href: 'https://drive.google.com/file/d/1hBPFUSHKHD27TzsUo_4P5WzrtgShFKRg/view?usp=sharing',
        },
        {
          name: 'Greene County Public Transit',
          href: 'https://drive.google.com/file/d/181zOBUGowcSp_mpT_NL0l1pkfsbpjeQn/view?usp=sharing',
        },
        {
          name: 'Gwinnett County Transit',
          href: 'https://drive.google.com/file/d/16mxSP3LRm8wZLavEQ-psu3sJUiXLZ5uX/view?usp=sharing',
        },
        {
          name: 'Habersham County Transit',
          href: 'https://drive.google.com/file/d/1xWsEr6c2POLHqIT3my2BAaZTEiTVgG7A/view?usp=sharing',
        },
        {
          name: 'Hall Area Transit',
          href: 'https://drive.google.com/file/d/1_b2m_Gb2UpnPQCcj16CMg0lSVCAxytVR/view?usp=sharing',
        },
        {
          name: 'Hancock County Transit',
          href: 'https://drive.google.com/file/d/1c2-yZ6aGEJpWJuiq_yWL7EH00e_SiYyq/view?usp=sharing',
        },
        {
          name: 'Haralson County Transit',
          href: 'https://drive.google.com/file/d/1wJ_xWt4uTM9fQO7pzVCsj-TViDa7E2TH/view?usp=sharing',
        },
        {
          name: 'Hart Transit',
          href: 'https://drive.google.com/file/d/1Yatyfl9GeNMtZjmCMRMq64YPae3kMW5o/view?usp=sharing',
        },
        {
          name: 'Heard County Transit',
          href: 'https://drive.google.com/file/d/1KruyFVxtlh94-ENmVc3n2-DhHfsR9bXC/view?usp=sharing',
        },
        {
          name: 'Henry County Transit',
          href: 'https://drive.google.com/file/d/1nwTSWn3Q5B-l1nfc6Gbh1F3XOHPNHxFO/view?usp=sharing',
        },
        {
          name: 'Jackson County Transit',
          href: 'https://drive.google.com/file/d/1OCiQGlMmh358K7Ny5uDh52DS58P-t1Ib/view?usp=sharing',
        },
        {
          name: 'Jefferson Transit',
          href: 'https://drive.google.com/file/d/1itvT2dXqX2-JOiMSJoWuGtZEW9zR3fMU/view?usp=sharing',
        },
        {
          name: 'Jenkins County Transit',
          href: 'https://drive.google.com/file/d/1-xcniEBYpLaKTWtJq24hz1vZmXxCaxmI/view?usp=sharing',
        },
        {
          name: 'Jones County Transit',
          href: 'https://drive.google.com/file/d/1b8DGWo3vwhkrPVrN__kr9KI_8K1ky9Gl/view?usp=sharing',
        },
        {
          name: 'Liberty Transit',
          href: 'https://drive.google.com/file/d/193hbl7VGHcMYTzURzOcRQST3Jp9yhXdB/view?usp=sharing',
        },
        {
          name: 'Lincoln County Transit',
          href: 'https://drive.google.com/file/d/1-cUSUuayX055IjDeardrKKBzK9EAX5nu/view?usp=sharing',
        },
        {
          name: 'Lower Chattahoochee Regional Transportation Authority',
          href: 'https://drive.google.com/file/d/1q8YffGmZUCue3FNyDk0ehXZFWa4bAVLE/view?usp=sharing',
        },
        {
          name: 'Lowndes County Transit',
          href: 'https://drive.google.com/file/d/1lEI_y0tDij5MVVe9NBr4Qw8qG8UEuw4V/view?usp=sharing',
        },
        {
          name: 'Lumpkin County Transit',
          href: 'https://drive.google.com/file/d/1CZDrktbrBcId2ggWZ7VI_OPIxS5s9eGg/view?usp=sharing',
        },
        {
          name: 'Macon County Transit',
          href: 'https://drive.google.com/file/d/1KLllI99aZsLpKb2oUGmjjfEcK-gpjGCd/view?usp=sharing',
        },
        {
          name: 'Macon-Bobb County Transit Authority',
          href: 'https://drive.google.com/file/d/19FmfTnLRiSgB8qS3OXoLGGSMBeZIiRHe/view?usp=sharing',
        },
        {
          name: 'McDuffie County Rural Transportation System',
          href: 'https://drive.google.com/file/d/1wf1TAJupW5RcC09OHOH_Yfpn8EyUo_EO/view?usp=sharing',
        },
        {
          name: 'METRA Transit',
          href: 'https://drive.google.com/file/d/1ucm1CG2XJO5jHFEoPk6YozUsyBM_hwGI/view?usp=sharing',
        },
        {
          name: 'Metropolitan Atlanta Rapid Transit Authority (MARTA)',
          href: 'https://drive.google.com/file/d/14wuCeJixIOdSaAfbnFuW55-jucsXWB94/view?usp=sharing',
        },
        {
          name: 'Morgan County Transportation System',
          href: 'https://drive.google.com/file/d/1IdAdA2SX-mvHjm2c0OKTmLOL6qRaRqPt/view?usp=sharing',
        },
        {
          name: 'Mountain Area Transportation System',
          href: 'https://drive.google.com/file/d/15SE-kPzGhfFb9z2M2IfLv30EhiT7eQci/view?usp=sharing',
        },
        {
          name: 'Murray County Transportation System',
          href: 'https://drive.google.com/file/d/1KDwdMduEJ4darY1dp7FwpshYSiPqTLiK/view?usp=sharing',
        },
        {
          name: 'Paulding Transit',
          href: 'https://drive.google.com/file/d/1uV_HWBs2HFm531wiQLJFYlM88euOurTP/view?usp=sharing',
        },
        {
          name: 'Peach County Transit',
          href: 'https://drive.google.com/file/d/1saaijEdP1BVhxleZvO2h9hf8tEWZC2jg/view?usp=sharing',
        },
        {
          name: 'Pierce Transit',
          href: 'https://drive.google.com/file/d/18_0tWETmC-5oKW14pMOpC7jzkS7jc-5t/view?usp=sharing',
        },
        {
          name: 'Pulaski County Transit',
          href: 'https://drive.google.com/file/d/10rilVFqENOtrfL7Eph7-q0p3wGRvVkRD/view?usp=sharing',
        },
        {
          name: 'Putnam Transit',
          href: 'https://drive.google.com/file/d/1UHLJAKJQg_79DGjju94GvyISbnlS4Y63/view?usp=sharing',
        },
        {
          name: 'Rabun County Public Transportation',
          href: 'https://drive.google.com/file/d/1zkRnX_Pus69lngA_KVdNPPNhcgM4RSQ2/view?usp=sharing',
        },
        {
          name: 'Rome Transit',
          href: 'https://drive.google.com/file/d/1aoC9bNAC2Cw9L6sn-PP8M8MZTxKDF_DA/view?usp=sharing',
        },
        {
          name: 'Social Circle Transit',
          href: 'https://drive.google.com/file/d/1syZ9q2B7195jB4-i40AXuaA3b8vjLao8/view?usp=sharing',
        },
        {
          name: 'Southwest Georgia Regional Transit',
          href: 'https://drive.google.com/file/d/15NVRE2nqNNa0kMDpQCoiQMzN0O5xOznx/view?usp=sharing',
        },
        {
          name: 'SRTA Xpress',
          href: 'https://drive.google.com/file/d/1QAFexiV1qukKYLmKrXIWt2kWDXMyz0Ys/view?usp=sharing',
        },
        {
          name: 'Talbot County Transit',
          href: 'https://drive.google.com/file/d/1aA5EBhru5vAGSiJmg3kdnnEnxqneLwVr/view?usp=sharing',
        },
        {
          name: 'Taliaferro County Transit',
          href: 'https://drive.google.com/file/d/1PNf5OBwlnZPEahObmlI6p7oFu2pijK_v/view?usp=sharing',
        },
        {
          name: 'Taylor County Transit Authority',
          href: 'https://drive.google.com/file/d/1XFTEO2ReqtuVWFUGIMIIK7Vw06FOUP-U/view?usp=sharing',
        },
        {
          name: 'Telfair County Transit',
          href: 'https://drive.google.com/file/d/1_WZ0co6TVj6RSuSlZyRe65e9fHkvYftZ/view?usp=sharing',
        },
        {
          name: 'Thomas County Area Transit',
          href: 'https://drive.google.com/file/d/1mmfXTD7tRDJmzYu6O4KglK6tuMvLNo0q/view?usp=sharing',
        },
        {
          name: 'Three Rivers Regional Transit System',
          href: 'https://drive.google.com/file/d/1PGZX9DCF3mPMA3Cn_N59oCzS79-1mcC7/view?usp=sharing',
        },
        {
          name: 'Tift Lift',
          href: 'https://drive.google.com/file/d/1h0d7EPHmgXp0KQ49XUbWURu_ONR5j06l/view?usp=sharing',
        },
        {
          name: 'Towns County Transit',
          href: 'https://drive.google.com/file/d/13Iu4qYNswyKTLgR9CXh7BpHUmtWx2aIL/view?usp=sharing',
        },
        {
          name: 'Troup Transit',
          href: 'https://drive.google.com/file/d/1xKbk_WzinXrDB0d3L1EDY3J3cX4TAsND/view?usp=sharing',
        },
        {
          name: 'Turner Transit',
          href: 'https://drive.google.com/file/d/1ltTR3UfUTxcYvutNBlE90XHRdVkA3NVY/view?usp=sharing',
        },
        {
          name: 'Twiggs County Transit',
          href: 'https://drive.google.com/file/d/1EWHLwfQWmeK5CDaY385JzlIvKcC6NOUm/view?usp=sharing',
        },
        {
          name: 'Union County Transportation',
          href: 'https://drive.google.com/file/d/1ivzMYMRUEYQSTg3B8YSs6oKR8DbjQKPp/view?usp=sharing',
        },
        {
          name: 'Walker Transit',
          href: 'https://drive.google.com/file/d/15w7Ana0WEtrLeq0NvHf0C_O8s2Ofc1CC/view?usp=sharing',
        },
        {
          name: 'Ware County Transit',
          href: 'https://drive.google.com/file/d/19rtNmeTUNBvnaRAg2Yo1-cHM9ZpN3B_N/view?usp=sharing',
        },
        {
          name: 'Warren County Transit',
          href: 'https://drive.google.com/file/d/1VzTYS8S5x7A9MGI6xTu9YfvNRol23_dp/view?usp=sharing',
        },
        {
          name: 'Wayne County Transit',
          href: 'https://drive.google.com/file/d/1KhUc1njUd7ctsYzoEVdBK6iTMPfwnJDq/view?usp=sharing',
        },
        {
          name: 'Wheeler County Transit System',
          href: 'https://drive.google.com/file/d/1LvfcGLWaokwQBNKu70iempKilgUAxSU1/view?usp=sharing',
        },
        {
          name: 'Whitfield County Transit',
          href: 'https://drive.google.com/file/d/18MNFhb4sk_gha3leqqAyYUvmMzFw7Fkl/view?usp=sharing',
        },
        {
          name: 'Wilcox Transit',
          href: 'https://drive.google.com/file/d/1U6dL3KoIEEJmpBnD9VsSUEuXGlOYGkgT/view?usp=sharing',
        },
        {
          name: 'Wilkes County Commission Transit',
          href: 'https://drive.google.com/file/d/1uDQrtgwFzSA5V_CEnUR-GCMen08eY9Ss/view?usp=sharing',
        },
        {
          name: 'Wilkinson County Transit',
          href: 'https://drive.google.com/file/d/1stwjwa3WXUkdGworA8UKv0etP1oL2WU7/view?usp=sharing',
        }
      ]
  }
  }
};
</script>
