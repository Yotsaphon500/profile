<template>
  <div class="d-flex align-items-center min-vh-100">
    <CContainer fluid>
      <CRow class="justify-content-center">
        <CCol md="6">
          <CCard class="mx-4 mb-0">
            <CCardBody class="p-4">
              <CForm>
                <CRow>
                  <CCol sm="3">
                    <div id="circle"></div>
                  </CCol>
                  <CCol style="margin-top:5%" sm="5">
                    <h5>Name:Test Test</h5>
                    <p class="text-muted">User ID : 5712315315</p>
                  </CCol>
                </CRow>
                  <p class="text-muted" style="margin-top: 5%;">Name</p>
                <div class="form-group" role="group">
                  <CRow>
                      <CCol sm="4">
                        <CInput
                          label="First name"
                          v-model="username"
                        />
                      </CCol>
                      <CCol sm="4">
                        <CInput
                          label="Surname"
                          v-model="usersurname"
                        />
                      </CCol>
                      <CCol sm="4">
                        <CSelect
                          v-model="gender"
                          label="Gender"
                          :options="['...','Men','Women']"
                          
                        />
                      </CCol>
                  </CRow>
                </div>

                <div class="form-group" role="group" style="margin-top:3%">
                  <p class="text-muted">Birthday</p>
                  <div>
                    <CRow>
                      <CCol sm="2">
                        <CSelect
                          v-model="date"
                          label="Date"
                          :options="[1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31]"
                          
                        />
                      </CCol>
                      <CCol sm="2">
                        <CSelect
                          v-model="month"
                          label="Month"
                          :options="[1,2,3,4,5,6,7,8,9,10,11,12]"
                        />
                      </CCol>
                      <CCol sm="2">
                        <CSelect
                          v-model="year"
                          label="Year"
                          :options="[1980,1981,1982,1983,1984,1985,1986,1987
                          ,1988,1989,1990,1991,1992,1993,1994,1995,1996,1997
                          ,1998,1999,2000,2001,2002,2003,2004,2005,2006,2007
                          ,2008,2009,2010,2011,2012,2013,2014,2015,2016,2017
                          ,2018,2019,2020]"
                        />
                      </CCol>
                      <CCol sm="2">
                        <CInput
                          label="Age"
                          v-model="age"
                        />
                      </CCol>
                      <CCol sm="4">
                        <CInput
                          label="Phone number"
                          v-model="phoneNumber"
                        />
                      </CCol>
                  </CRow>
                  </div>
                </div>

                <div class="form-group" role="group" style="margin-top:3%">
                  <p class="text-muted">Country</p>
                  <CSelect
                    v-model="country"
                    horizontal
                    :options="options"
                    placeholder="Please select"
                  />
                </div>

                <div class="form-group" role="group" style="margin-top:3%">
                  <CRow
                    class="form-group"
                    v-for="(number, key) in [6]"
                    :key="key"
                  >
                    <CCol :col="12 - number">
                      <CInput v-model="zipcode" label="Zipcode" class="mb-0" id="zipcode"/>
                    </CCol>
                    <CCol :col="number">
                      <CSelect v-model="state" label="Province/State" class="mb-0" placeholder="Please select" :options="options"/>
                    </CCol>
                  </CRow>
                </div>
                
                <div class="form-group" role="group" style="margin-top:3%">
                  <CRow
                    class="form-group"
                    v-for="(number, key) in [6]"
                    :key="key"
                  >
                    <CCol :col="12 - number">
                      <CSelect v-model="district" label="District" class="mb-0" :options="options"/>
                    </CCol>
                    <CCol :col="number">
                      <CSelect v-model="subDistrict" label="Sub-District" class="mb-0" placeholder="Please select" :options="options"/>
                    </CCol>
                  </CRow>
                </div>

                <div class="form-group" role="group" style="margin-top:3%">
                  <p class="text-muted">Address</p>
                  <CInput v-model="address" />
                </div>

                <div class="form-group" role="group" style="margin-top:3%">
                  <p class="text-muted">Occupation</p>
                  <CSelect
                    v-model="occupation"
                    horizontal
                    :options="options"
                    placeholder="Please select"
                  />
                </div>

                <div class="form-group" role="group" style="margin-top:3%">
                  <CRow
                    class="form-group"
                    v-for="(number, key) in [6]"
                    :key="key"
                  >
                    <CCol :col="12 - number">
                      <CInput v-model="university" label="University" class="mb-0"/>
                    </CCol>
                    <CCol :col="number">
                      <CInput v-model="school" label="Faculity/School" class="mb-0" placeholder="Please select" :options="options"/>
                    </CCol>
                  </CRow>
                </div>

                <div class="form-group" role="group" style="margin-top:3%">
                  <p class="text-muted">Major</p>
                  <CInput v-model="major" />
                </div>
              </CForm>
            </CCardBody>
            <cRow>
              <CCol>
                <Button class="facebookButton">Facebook</Button>
              </CCol>
            </cRow>
            <cRow>
              <CCol>
                <Button class="googleButton">Google</Button>
              </CCol>
            </cRow>
            <cRow>
              <CCol>
                <div style="text-align: right;">
                  <Button @click="this.onRegister" class="updateButton">Register</Button>
                  <Button class="cancelButton">Cancel</Button>
                </div>
              </CCol>
            </cRow>
          </CCard>
        </CCol>
      </CRow>
    </CContainer>
  </div>
</template>

<script>
export default {
  name: 'RegisterYot',
  data () {
    return {
      // selected: [], // Must be an array reference!
      // show: true,
      // horizontal: { label:'col-3', input:'col-9' },
      options: ['Option 1', 'Option 2', 'Option 3'],
      // selectOptions: [
      //   'Option 1', 'Option 2', 'Option 3',
      //   { 
      //     value: ['some value', 'another value'], 
      //     label: 'Selected option'
      //   }
      // ],
      // selectedOption: ['some value', 'another value'],

      // formCollapsed: true,
      // checkboxNames: ['Checkboxes', 'Inline Checkboxes',
      //                 'Checkboxes - custom', 'Inline Checkboxes - custom'],
      // radioNames: ['Radios', 'Inline Radios',
      //               'Radios - custom', 'Inline Radios - custom']
    }
  },
  userInfo () {
    return{
      username:'',
      usersurname:'',
      gender:'',
      date:'',
      month:'',
      year:'',
      age:'',
      phoneNumber:'',
      country:'',
      zipcode:'',
      state:'',
      district:'',
      subDistrict:'',
      address:'',
      occupation:'',
      university:'',
      school:'',
      major:''
    }
  },
  methods: {
    validator (val) {
      return val ? val.length >= 4 : false
    },
    onRegister(){
      var info = {};
      info.username=this.username;
      info.usersurname=this.usersurname;
      info.gender=this.gender;
      info.date=this.date;
      info.month=this.month;
      info.year=this.year;
      info.age=this.age;
      info.phoneNumber=this.phoneNumber;
      info.country=this.country;
      info.zipcode=this.zipcode;
      info.state=this.state;
      info.district=this.district;
      info.subDistrict=this.subDistrict;
      info.address=this.address;
      info.occupation=this.occupation;
      info.university=this.university;
      info.school=this.school;
      info.major=this.major;

      console.log(info);

    }
  }
}
</script>
<style>
#circle {
  width: 140px;
  height: 140px;
  background: white;
  border-radius: 70px;
  border: gray;
  border-style: solid;
  border-width: medium;
}.facebookButton {
  border: 3px solid blue;
  height: 35px;
  width: 40%;
  background-color: white;
  color: blue;
  margin-left: 4%;
}
.googleButton {
  background-color: white;
  color: orange;
  border: 3px solid red;
  height: 35px;
  width: 40%;
  margin-top: 3%;
  margin-left: 4%;
}
.updateButton {
  background-color: #81dbfc;
  border-radius: 8px;
  color: white;
  height: 35px;
}
.cancelButton {
  background-color: gray;
  border-radius: 8px;
  color: white;
  height: 35px;
  margin-left: 1%;
  margin-right: 5%;
  margin-bottom: 20%;
}
</style>