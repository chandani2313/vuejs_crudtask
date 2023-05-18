<template>
  <div class="col-md-6 tabt">
    <table class="table">
      <tbody>
        <tr class="ztxt">
          <th>Name</th>
          <th>Email</th>
          <th>Phone</th>
          <th>address1</th>
          <th>address2</th>
          <th>city</th>
          <th>state</th>
          <th>zipCode</th>
          <th>country</th>
          <th>qualification</th>
          <th>comments</th>
        </tr>
        <tr v-for="user in filteredUsers" :key="user.id">
          <td>{{ user.firstName }}{{ user.lastName }}</td>
          <td>{{ user.email }}</td>
          <td>{{ user.phoneNumber }}</td>
          <td>{{ user.address1 }}</td>
          <td>{{ user.address2 }}</td>
          <td>{{ user.city }}</td>
          <td>{{ user.state }}</td>
          <td>{{ user.zipCode }}</td>
          <td>{{ user.country }}</td>
          <td>{{ user.qualification }}</td>
          <td>{{ user.comments }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
<script setup>
import { ref, computed } from "vue";
import { useRoute } from "vue-router";
const form = ref([
  {
    id: 12,
    firstName: "Raju",
    lastName: "example",
    email: "raj@example.com",
    phoneNumber: "1111222233",
    address1: "sample",
    address2: "sample",
    city: "sample",
    state: "sample",
    zipCode: "111111",
    country: "sample",
    qualification: "sample",
    comments: "sample",
  },
  {
    id: 33,
    firstName: "Rio",
    lastName: "V",
    email: "rio@example.com",
    phoneNumber: "9865566122",
    address1: "Do.no.1895, Bharathi Street,",
    address2: "Shenoy Nagar",
    city: "Chennai",
    state: "TamilNadu",
    zipCode: "600026",
    country: "India",
    qualification: "B.E(Mech)",
    comments: "No Comments",
  },
  {
    id: 34,
    firstName: "Gowtham",
    lastName: "S",
    email: "gowtham1018@gmail.com",
    phoneNumber: "8825722799",
    address1: "Do.No.198, Bharathi Street,",
    address2: "Near Bus Stand, Kambar Nagar",
    city: "Coimbatore",
    state: "TamilNadu",
    zipCode: "682310",
    country: "India",
    qualification: "B.E(IT)",
    comments: "No Comments",
  },
  {
    id: 35,
    firstName: "Vivek",
    lastName: "R",
    email: "vivek@gmail.com",
    phoneNumber: "8754976656",
    address1: "Do.no.5688, MG Street,",
    address2: "Raman Nagar,",
    city: "Erode",
    state: "TamilNadu",
    zipCode: "605022",
    country: "India",
    qualification: "B.E(Mech)",
    comments: "No Comments",
  },
  {
    id: 36,
    firstName: "Anu",
    lastName: "D",
    email: "anujai@gmail.com",
    phoneNumber: "6984698898",
    address1: "Do.No.698, Murugan Street,",
    address2: "Anna Nagar,",
    city: "Puducherry",
    state: "Puducherry",
    zipCode: "605001",
    country: "India",
    qualification: "B.E(IT)",
    comments: "No Comments",
  },
  {
    id: 37,
    firstName: "example",
    lastName: "example",
    email: "example@example.com",
    phoneNumber: "1111222233",
    address1: "sample",
    address2: "sample",
    city: "sample",
    state: "sample",
    zipCode: "111111",
    country: "sample",
    qualification: "sample",
    comments: "sample",
  },
]);
const route = useRoute();

const filteredUsers = computed(() => {
  const userId = Number(route.params.id);
  return form.value.filter((user) => user.id === userId);
});
</script>
<style scoped></style>
