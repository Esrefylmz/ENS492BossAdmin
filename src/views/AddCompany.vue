<template>
    <div class="add-company-form">
      <h1>Create Company</h1>
  
      <form @submit.prevent="submit">

  
        <div class="form-group">
          <label for="companyName">Company Name:</label>
          <input type="text" id="companyName" v-model="companyName" required>
        </div>
  
        <div class="form-group">
          <label for="domain">Domain:</label>
          <input type="text" id="domain" v-model="domain" required>
        </div>
  
        <div class="form-group">
          <label for="ssid">SSID:</label>
          <input type="text" id="ssid" v-model="ssid" required>
        </div>
  
        <div class="form-group">
          <label for="broker">Broker:</label>
          <input type="text" id="broker" v-model="broker" required>
        </div>
  
        <div class="form-group">
          <label for="password">Password:</label>
          <input type="password" id="password" v-model="password" required>
        </div>
  
        <div class="form-group">
          <button type="submit">Create Company</button>
        </div>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {

        companyName: '',
        domain: '',
        ssid: '',
        broker: '',
        password: '',
      };
    },
    methods: {
      submit() {
        fetch('http://localhost:5063/api/CompanyContoller/CreateCompany', {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json',
          },
          body: JSON.stringify({

            name: this.companyName,
            domain: this.domain,
            ssid: this.ssid,
            broker: this.broker,
            password: this.password,
          }),
        })
          .then((response) => {
            if (!response.ok) {
              throw new Error('Error submitting form data');
            }
            return response.json();
          })
          .then((data) => {
            // Handle success response here
            console.log('Company created successfully:', data);
            // Redirect user to success page or perform other actions as needed
          })
          .catch((error) => {
            console.error('Error submitting form data:', error);
          });
      },
    },
  };
  </script>
  
  <style>
  .add-company-form {
    padding: 20px;
  }
  .form-group {
    margin-bottom: 20px;
  }
  label {
    display: block;
    margin-top: 5px;
    margin-bottom: 5px;
    font-weight: bold;
  }
  input[type='text'], input[type='number'], input[type='password'] {
    width: 60%;
    margin: 10px;
    padding: 10px;
    border-radius: 5px;
    border: 1px solid #ccc;
  }
  button[type='submit'] {
    background-color: green;
    color: white;
    border: none;
    border-radius: 20px;
    width: 30%;
    height: 60px;
    font-size: 24
  }