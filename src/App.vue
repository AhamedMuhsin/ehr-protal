<template>
    <div>
        <h1>Welcome to the App</h1>
        <router-link to="/payslip">
            <button class="p-2 bg-blue-500 text-white rounded">Go to Payslip</button>
        </router-link>
        <router-view />
    </div>
</template>