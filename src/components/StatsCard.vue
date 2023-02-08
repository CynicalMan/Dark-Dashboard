<template>
    <div class="flex gap-6">
        <div v-for="stat in stats" class="flex flex-col p-4 w-1/3 bg-gray-900 rounded-lg gap-y-3">
            <div class="flex items-center gap-x-3">
                <div class="p-2 bg-gray-800 rounded-lg">
                    <component :is="stat.icon"></component>
                </div>
                <span class="text-xs font-medium" 
                :class="stat.status === 'up'
                ? 'text-accent-green'
                :'text-accent-red'">
                    {{ stat.percentage }}
                </span>
                <div class="p-0.5 rounded-full" :class="stat.status === 'up' ? 'bg-accent-green/20' : 'bg-accent-red/20'">
                    <ArrowUpIcon v-if="stat.status === 'up'" class="fill-current text-accent-green" />
                    <ArrowDownIcon v-else class="fill-current text-accent-red" />
                </div>
            </div>
            <div class="text-3xl font-semibold text-white">{{ stat.value }}</div>
            <div class="text-sm tracking-wide text-gray-50">{{ stat.title }}</div>
        </div>
    </div>
</template>

<script setup>
import CoinIcon from '../assets/icons/coin.svg';
import OrderIcon from '../assets/icons/order.svg';
import CustomerIcon from '../assets/icons/customer.svg';
import ArrowUpIcon from '../assets/icons/arrow-up.svg'
import ArrowDownIcon from '../assets/icons/arrow-down.svg'

const stats = [
    {
        title: 'Total Revenue',
        percentage: '+32.40%',
        value: '$10,345.00',
        status: 'up',
        icon: CoinIcon,
    },
    {
        title: 'Total Dish Ordered',
        percentage: '-12.40%',
        value: '23,456',
        status: 'down',
        icon: OrderIcon,
    },
    {
        title: 'Total Customer',
        percentage: '+2.40%',
        value: '1,234',
        status: 'up',
        icon: CustomerIcon,
    },
];

</script>

<style>
    
</style>