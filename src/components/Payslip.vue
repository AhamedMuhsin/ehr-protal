<template>
    <div class="payslip-container">
        <sv-card class="p-6 shadow-lg">
            <h2 class="text-2xl font-bold mb-4">Employee Payslip</h2>
            <sv-divider />

            <div class="grid grid-cols-2 gap-4">
                <div>
                    <p class="font-semibold">Employee Name:</p>
                    <p>{{ employee.name }}</p>
                </div>
                <div>
                    <p class="font-semibold">Employee ID:</p>
                    <p>{{ employee.id }}</p>
                </div>
                <div>
                    <p class="font-semibold">Department:</p>
                    <p>{{ employee.department }}</p>
                </div>
                <div>
                    <p class="font-semibold">Date:</p>
                    <p>{{ employee.date }}</p>
                </div>
                <div>
                    <p class="font-semibold" style="display: inline">Finance Year :</p>
                    <select>
                        <option value="2023" selected>2023</option>
                        <option value="2024">2024</option>
                        <option value="2022">2022</option>
                    </select>
                </div>
            </div>

            <sv-divider />
            <table class="w-full mt-4 border">
                <thead>
                    <tr class="bg-gray-200">
                        <th class="py-2 px-4 text-left">Period</th>
                        <th class="py-2 px-4 text-left">View Profile</th>
                        <th class="py-2 px-4 text-right">Month</th>
                        <th class="py-2 px-4 text-right">Gerented On</th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="(item, index) in earnings" :key="index">
                        <td class="py-2 px-4 text-left">{{ item.period }}</td>
                        <td class="py-2 px-4 text-left">{{ item.view }}</td>
                        <td class="py-2 px-4 text-right">{{ item.month }}</td>
                        <td class="py-2 px-4 text-right">{{ item.gerented }}</td>
                    </tr>
                </tbody>
            </table>

            <sv-divider />

            <!-- <div class="flex justify-between font-semibold mt-4">
                <p>Total Earnings:</p>
                <p>₹{{ totalEarnings }}</p>
            </div>

            <sv-alert type="success" class="mt-4"> Net Pay: ₹{{ totalEarnings }} </sv-alert> -->
        </sv-card>
    </div>
</template>

<script>
export default {
    data() {
        return {
            employee: {
                name: 'Ahamed Muhsin',
                id: 'EMP123',
                department: 'Software Development',
                date: new Date().toLocaleDateString('en-US', { month: 'long', year: 'numeric' })

            },
            earnings: [
                { period: new Date().toLocaleDateString(), view: 'Compact', month: new Date().toLocaleDateString('en-US', { month: 'long', year: 'numeric' }), gerented: new Date().toLocaleDateString('en-US', { weekday : 'short', day: 'numeric',month: 'long', year: 'numeric' }) },
                { period: new Date().toLocaleDateString(), view: 'Compact', month: new Date().toLocaleDateString('en-US', { month: 'long', year: 'numeric' }), gerented: new Date().toLocaleDateString('en-US', { weekday : 'short', day: 'numeric',month: 'long', year: 'numeric' }) },
                { period: new Date().toLocaleDateString(), view: 'Yet to be Published', month: new Date().toLocaleDateString('en-US', { month: 'long', year: 'numeric' }), gerented: new Date().toLocaleDateString('en-US', { weekday : 'short', day: 'numeric',month: 'long', year: 'numeric' }) }
            ]
        };
    }
    // computed: {
    //     totalEarnings() {
    //         return this.earnings.reduce((sum, item) => sum + item.amount, 0);
    //     }
    // }
};
</script>

<style>
.payslip-container {
    max-width: 600px;
    margin: auto;
    padding: 20px;
    background-color: white;
}
</style>
