<script setup>
import Chart from 'primevue/chart';
import Card from 'primevue/card';

import Paginator from 'primevue/paginator';


import { ref, onMounted } from "vue";

    definePageMeta({
        layout: "dashboard",
    })

    onMounted(() => {
		setTimeout(function () {
			chartData.value = setChartData();
			lineData.value = setLineData();
            pieData.value = setPieData();
            barData.value = setBarData();
            // options
            pieOptions.value = setChartOptions();
		}, 500);
		
	});

	const chartData = ref();
	const lineData = ref();
	const pieData = ref();
	const barData = ref();
	const pieOptions = ref();

    const setChartData = () => {
        const documentStyle = getComputedStyle(document.documentElement);

        return {
            labels: ['01', '02', '04', '05', '06', '07', '08', '09', '10', '11', '12', '13', '14', '15', '16', '17', '18', '19', '20', '21', '22', '23', '24', '25', '26', '27', '28', '29', '30', '31'],
            datasets: [
                {
                    label: "This Month",
                
                    data: [65, 59, 80, 81, 56, 55, 40],
                    fill: true,
                    borderColor: documentStyle.getPropertyValue('--cyan-500'),
                    tension: 0.4
                },
                {
                    label: "Previous Month",
                    
                    data: [28, 48, 400, 19, 86, 27, 90],
                    fill: true,
                    borderColor: documentStyle.getPropertyValue('--gray-500'),
                    tension: 0.4
                }
            ]
        };
    };


    const setLineData = () => {
        const documentStyle = getComputedStyle(document.documentElement);

        return {
            labels: ['01', '02', '04', '05', '06', '07', '08', '09', '10', '11', '12', '13', '14', '15', '16', '17', '18', '19', '20', '21', '22', '23', '24', '25', '26', '27', '28', '29', '30', '31'],
            datasets: [
                {
                    label: "This Month",
                
                    data: [65, 59, 80, 81, 56, 55, 40],
                    fill: false,
                    borderColor: documentStyle.getPropertyValue('--cyan-500'),
                    backgroundColor: documentStyle.getPropertyValue('--cyan-500'),
                    tension: 0.4
                },
                {
                    label: "Previous Month",
                    
                    data: [28, 48, 400, 19, 86, 27, 90],
                    fill: false,
                    borderColor: documentStyle.getPropertyValue('--gray-500'),
                    backgroundColor: documentStyle.getPropertyValue('--gray-500'),
                    tension: 0.4
                }
            ]
        };
    };


    const setBarData = () => {
        const documentStyle = getComputedStyle(document.documentElement);

        return {
            labels: ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday'],
            datasets: [
                {
                    label: "This Week",
                
                    data: [65, 59, 80, 81, 56, 55, 40],
                    fill: false,
                    borderColor: documentStyle.getPropertyValue('--blue-500'),
                    backgroundColor: documentStyle.getPropertyValue('--blue-500'),
                    tension: 0.4
                },
                {
                    label: "Previous Week",
                    
                    data: [28, 48, 400, 19, 86, 27, 90],
                    fill: false,
                    borderColor: documentStyle.getPropertyValue('--gray-300'),
                    backgroundColor: documentStyle.getPropertyValue('--gray-300'),
                    tension: 0.4
                }
            ]
        };
    };


    const setPieData = () => {
        const documentStyle = getComputedStyle(document.documentElement);

        return {
            labels: ['Pending', 'Process', 'Packaging', 'Cancel', 'Rejected', 'Delivered'],
            datasets: [
                {
                
                    data: [65, 59, 80, 81, 56, 55],
                    fill: true,
                    // borderColor: [documentStyle.getPropertyValue('--green-700'), documentStyle.getPropertyValue('--blue-700'), documentStyle.getPropertyValue('--yellow-700'), documentStyle.getPropertyValue('--pink-700'), documentStyle.getPropertyValue('--red-700'), documentStyle.getPropertyValue('--green-500')],
                    backgroundColor: [documentStyle.getPropertyValue('--orange-600'), documentStyle.getPropertyValue('--blue-600'), documentStyle.getPropertyValue('--yellow-600'), documentStyle.getPropertyValue('--pink-600'), documentStyle.getPropertyValue('--red-600'),documentStyle.getPropertyValue('--green-600')],
                    tension: 0.4
                }
            ]
        };
    };

    const setChartOptions = () => {
    const documentStyle = getComputedStyle(document.documentElement);

    return {
        plugins: {
            legend: {
                display: false,
                position: "left"
            }
            
        }
    };
};




</script>

<template>
    <NuxtLayout :name="layout">
        <div class="w-full px-3 mt-1">

            <div class="grid grid-cols-4 gap-3 w-full">
                <!-- Total Sales -->
                <div class="shadow-md bg-white w-full h-36 overflow-hidden rounded-md relative">
                    <div class="flex w-full px-3 pt-3">
                        <div class="bg-red-100 w-8 h-8 flex items-center rounded-md">
                            <Icon class="text-center w-full text-yellow-500"  name="mdi:checkbox-marked-circle-outline" width="1.4em" height="1.4em" />
                        </div>
                        <div class="font-semibold mt-1 ml-1">Total Sales</div>
                        
                    </div>

                    <div class="flex w-full justify-between">
                        <div class="font-bold mt-1 ml-3 text-lg ">
                            $56,2554
                        </div>
                        
                        <div class="text-xs mr-3">
                            <div class="flex w-full justify-end text-green-600 -mt-2">
                                <Icon class="text-right"  name="ph:arrow-up-right-bold" width="1.4em" height="1.4em" /> 
                                <div>10.2</div>
                            </div>
                            
                            <div class="w-full ">+1.01% This week</div>
                        </div>
                        
                    </div>
                    <div class="absolute -bottom-1 -left-1 w-full">
                        <svg id="Layer_1" data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 429 109.61">
                            <path class="opacity-20 scale-y-[1.2] w-full" fill="#FFD700" stroke="orange" stroke-width="4" d="m395.56,66.21c-1.72-1.09-3.89-1.57-5.86-1.6-6.61-.09-13.22.2-19.83.25-7.27.06-9.64-1.95-11.93-10.28-.94-3.41-1.47-6.98-2.32-10.43-1.34-5.49-3.26-6.79-7.93-5.53-6.13,1.65-12.25,3.4-18.39,5-1.84.48-3.73.76-5.61.82-2.93.1-4.98,1.8-6.21,4.79-1.53,3.71-4.17,4.59-7.1,4.04-4.18-.78-7.6-.25-9.82,4.78-1.03,2.34-3.04,3.49-5.22,3.07-5.58-1.09-11.2-2.06-16.65-3.79-3.52-1.12-4.66-4.91-4.64-9.23.02-4.4-1.81-7.18-5.3-8.53-3.58-1.39-6.4-.11-7.8,4.33-1.28,4.05-3.72,5.05-6.81,5.15-1.18.04-2.36-.1-3.54-.17-1.74-.1-3.08.47-4.29,2.24-3.31,4.85-7.34,5.06-10.09-.24-4.5-8.66-11.02-14.35-17.69-20.08-3.59-3.09-7.2-5.29-11.74-4.56-2.95.47-5.35-.97-7.46-3.38-5.65-6.46-11.34-12.88-17.01-19.33-3.79-4.32-6.73-3.9-10.57.36-6.48,7.19-9.62,16.72-13.31,25.9-.48,1.19-.83,2.47-1.37,3.62-2.03,4.26-5.73,5.54-9.33,3.29-.84-.52-1.63-1.15-2.45-1.71-4.4-3.06-7.71-2.71-10.81,2.06-5.21,8.01-12.47,12.24-19.68,16.69-2.31,1.43-4.22.35-6.16-1.11-3.16-2.37-4.07-2.23-6.83.8-.47.51-.92,1.04-1.38,1.55-2.88,3.18-4.38,3.47-7.87,1.54-3.57-1.97-4.36-1.73-6.7,2.06-3.14,5.07-7.1,5.69-10.1.63-3.34-5.63-7.06-5.68-12.07-4.32-7.49,2.04-15.15,3.36-22.8,4.28-2.2.26-4.89-1.43-6.86-3.09-2.97-2.52-5.69-2.48-8.84-.91-2.75,1.37-5.6,2.64-8.5,3.34-1.9.46-3.99-.1-5.97-.36-.76-.1-1.47-.65-2.21-.98-2.64-1.15-5.14-3.51-8-2.22v54.14h428v-21.25c-2.99-1.92-5.99-3.82-8.96-5.79-7.99-5.29-15.92-10.73-23.98-15.86Z"/>
                        </svg>
                    </div>
                </div>

                <!-- Total Orders -->
                <div class="shadow-md bg-white w-full h-36 overflow-hidden rounded-md relative">
                    <div class="flex w-full px-3 pt-3">
                        <div class="bg-red-100 w-8 h-8 flex items-center rounded-md">
                            <Icon class="text-center w-full text-red-500"  name="grommet-icons:basket" width="1em" height="1em" />
                        </div>
                        <div class="font-semibold mt-1 ml-1">Total Orders</div>
                        
                    </div>

                    <div class="flex w-full justify-between">
                        <div class="font-bold mt-1 ml-3 text-lg ">
                            $20,2554
                        </div>
                        
                        <div class="text-xs mr-3">
                            <div class="flex w-full justify-end text-red-600 -mt-2">
                                <Icon class="text-right"  name="ph:arrow-down-right-bold" width="1.4em" height="1.4em" /> 
                                <div>10.2</div>
                            </div>
                            
                            <div class="w-full ">-0.31% This week</div>
                        </div>
                        
                    </div>
                    <div class="absolute -bottom-1 -left-1 w-full">
                        <svg id="Layer_1" data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 429 109.61">
                            <path class="opacity-20 scale-y-[1.2] w-full" fill="pink" stroke="red" stroke-width="4" d="m395.56,66.21c-1.72-1.09-3.89-1.57-5.86-1.6-6.61-.09-13.22.2-19.83.25-7.27.06-9.64-1.95-11.93-10.28-.94-3.41-1.47-6.98-2.32-10.43-1.34-5.49-3.26-6.79-7.93-5.53-6.13,1.65-12.25,3.4-18.39,5-1.84.48-3.73.76-5.61.82-2.93.1-4.98,1.8-6.21,4.79-1.53,3.71-4.17,4.59-7.1,4.04-4.18-.78-7.6-.25-9.82,4.78-1.03,2.34-3.04,3.49-5.22,3.07-5.58-1.09-11.2-2.06-16.65-3.79-3.52-1.12-4.66-4.91-4.64-9.23.02-4.4-1.81-7.18-5.3-8.53-3.58-1.39-6.4-.11-7.8,4.33-1.28,4.05-3.72,5.05-6.81,5.15-1.18.04-2.36-.1-3.54-.17-1.74-.1-3.08.47-4.29,2.24-3.31,4.85-7.34,5.06-10.09-.24-4.5-8.66-11.02-14.35-17.69-20.08-3.59-3.09-7.2-5.29-11.74-4.56-2.95.47-5.35-.97-7.46-3.38-5.65-6.46-11.34-12.88-17.01-19.33-3.79-4.32-6.73-3.9-10.57.36-6.48,7.19-9.62,16.72-13.31,25.9-.48,1.19-.83,2.47-1.37,3.62-2.03,4.26-5.73,5.54-9.33,3.29-.84-.52-1.63-1.15-2.45-1.71-4.4-3.06-7.71-2.71-10.81,2.06-5.21,8.01-12.47,12.24-19.68,16.69-2.31,1.43-4.22.35-6.16-1.11-3.16-2.37-4.07-2.23-6.83.8-.47.51-.92,1.04-1.38,1.55-2.88,3.18-4.38,3.47-7.87,1.54-3.57-1.97-4.36-1.73-6.7,2.06-3.14,5.07-7.1,5.69-10.1.63-3.34-5.63-7.06-5.68-12.07-4.32-7.49,2.04-15.15,3.36-22.8,4.28-2.2.26-4.89-1.43-6.86-3.09-2.97-2.52-5.69-2.48-8.84-.91-2.75,1.37-5.6,2.64-8.5,3.34-1.9.46-3.99-.1-5.97-.36-.76-.1-1.47-.65-2.21-.98-2.64-1.15-5.14-3.51-8-2.22v54.14h428v-21.25c-2.99-1.92-5.99-3.82-8.96-5.79-7.99-5.29-15.92-10.73-23.98-15.86Z"/>
                        </svg>
                    </div>
                </div>

                <!-- Total Earnings -->
                <div class="shadow-md bg-white w-full h-36 overflow-hidden rounded-md relative">
                    <div class="flex w-full px-3 pt-3">
                        <div class="bg-green-100 w-8 h-8 flex items-center rounded-md">
                            <Icon class="text-center w-full text-green-500"  name="mynaui:dollar-square" width="1.5em" height="1.5em" />
                        </div>
                        <div class="font-semibold mt-1 ml-1">Total Earnings</div>
                        
                    </div>

                    <div class="flex w-full justify-between">
                        <div class="font-bold mt-1 ml-3 text-lg ">
                            $20,2554
                        </div>
                        
                        <div class="text-xs mr-3">
                            <div class="flex w-full justify-end text-green-600 -mt-2">
                                <Icon class="text-right"  name="ph:arrow-up-right-bold" width="1.4em" height="1.4em" /> 
                                <div>10.2</div>
                            </div>
                            
                            <div class="w-full ">+1.01% This week</div>
                        </div>
                        
                    </div>
                    <div class="absolute -bottom-1 -left-1 w-full">
                        <svg id="Layer_1" data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 429 109.61">
                            <path class="opacity-25 scale-y-[1.2] w-full" fill="#5dbb63" stroke="green" stroke-width="4" d="m395.56,66.21c-1.72-1.09-3.89-1.57-5.86-1.6-6.61-.09-13.22.2-19.83.25-7.27.06-9.64-1.95-11.93-10.28-.94-3.41-1.47-6.98-2.32-10.43-1.34-5.49-3.26-6.79-7.93-5.53-6.13,1.65-12.25,3.4-18.39,5-1.84.48-3.73.76-5.61.82-2.93.1-4.98,1.8-6.21,4.79-1.53,3.71-4.17,4.59-7.1,4.04-4.18-.78-7.6-.25-9.82,4.78-1.03,2.34-3.04,3.49-5.22,3.07-5.58-1.09-11.2-2.06-16.65-3.79-3.52-1.12-4.66-4.91-4.64-9.23.02-4.4-1.81-7.18-5.3-8.53-3.58-1.39-6.4-.11-7.8,4.33-1.28,4.05-3.72,5.05-6.81,5.15-1.18.04-2.36-.1-3.54-.17-1.74-.1-3.08.47-4.29,2.24-3.31,4.85-7.34,5.06-10.09-.24-4.5-8.66-11.02-14.35-17.69-20.08-3.59-3.09-7.2-5.29-11.74-4.56-2.95.47-5.35-.97-7.46-3.38-5.65-6.46-11.34-12.88-17.01-19.33-3.79-4.32-6.73-3.9-10.57.36-6.48,7.19-9.62,16.72-13.31,25.9-.48,1.19-.83,2.47-1.37,3.62-2.03,4.26-5.73,5.54-9.33,3.29-.84-.52-1.63-1.15-2.45-1.71-4.4-3.06-7.71-2.71-10.81,2.06-5.21,8.01-12.47,12.24-19.68,16.69-2.31,1.43-4.22.35-6.16-1.11-3.16-2.37-4.07-2.23-6.83.8-.47.51-.92,1.04-1.38,1.55-2.88,3.18-4.38,3.47-7.87,1.54-3.57-1.97-4.36-1.73-6.7,2.06-3.14,5.07-7.1,5.69-10.1.63-3.34-5.63-7.06-5.68-12.07-4.32-7.49,2.04-15.15,3.36-22.8,4.28-2.2.26-4.89-1.43-6.86-3.09-2.97-2.52-5.69-2.48-8.84-.91-2.75,1.37-5.6,2.64-8.5,3.34-1.9.46-3.99-.1-5.97-.36-.76-.1-1.47-.65-2.21-.98-2.64-1.15-5.14-3.51-8-2.22v54.14h428v-21.25c-2.99-1.92-5.99-3.82-8.96-5.79-7.99-5.29-15.92-10.73-23.98-15.86Z"/>
                        </svg>
                    </div>
                </div>


                <!-- Total Pay -->
                <div class="shadow-md bg-white w-full h-36 overflow-hidden rounded-md relative">
                    <div class="flex w-full px-3 pt-3">
                        <div class="bg-blue-100 w-8 h-8 flex items-center rounded-md">
                            <Icon class="text-center w-full text-blue-500"  name="tabler:credit-card-pay" width="1.5em" height="1.5em" />
                        </div>
                        <div class="font-semibold mt-1 ml-1">Total Pays</div>
                        
                    </div>

                    <div class="flex w-full justify-between">
                        <div class="font-bold mt-1 ml-3 text-lg ">
                            $20,2554
                        </div>
                        
                        <div class="text-xs mr-3">
                            <div class="flex w-full justify-end text-green-600 -mt-2">
                                <Icon class="text-right"  name="ph:arrow-up-bold" width="1.4em" height="1.4em" /> 
                                <div>10.2</div>
                            </div>
                            
                            <div class="w-full ">+1.01% This week</div>
                        </div>
                        
                    </div>
                    <div class="absolute -bottom-1 -left-1 w-full">
                        <svg id="Layer_1" data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 429 109.61">
                            <path class="opacity-50 scale-y-[1.2] w-full" fill="#00008B" stroke="#1616FF" stroke-width="4" d="m395.56,66.21c-1.72-1.09-3.89-1.57-5.86-1.6-6.61-.09-13.22.2-19.83.25-7.27.06-9.64-1.95-11.93-10.28-.94-3.41-1.47-6.98-2.32-10.43-1.34-5.49-3.26-6.79-7.93-5.53-6.13,1.65-12.25,3.4-18.39,5-1.84.48-3.73.76-5.61.82-2.93.1-4.98,1.8-6.21,4.79-1.53,3.71-4.17,4.59-7.1,4.04-4.18-.78-7.6-.25-9.82,4.78-1.03,2.34-3.04,3.49-5.22,3.07-5.58-1.09-11.2-2.06-16.65-3.79-3.52-1.12-4.66-4.91-4.64-9.23.02-4.4-1.81-7.18-5.3-8.53-3.58-1.39-6.4-.11-7.8,4.33-1.28,4.05-3.72,5.05-6.81,5.15-1.18.04-2.36-.1-3.54-.17-1.74-.1-3.08.47-4.29,2.24-3.31,4.85-7.34,5.06-10.09-.24-4.5-8.66-11.02-14.35-17.69-20.08-3.59-3.09-7.2-5.29-11.74-4.56-2.95.47-5.35-.97-7.46-3.38-5.65-6.46-11.34-12.88-17.01-19.33-3.79-4.32-6.73-3.9-10.57.36-6.48,7.19-9.62,16.72-13.31,25.9-.48,1.19-.83,2.47-1.37,3.62-2.03,4.26-5.73,5.54-9.33,3.29-.84-.52-1.63-1.15-2.45-1.71-4.4-3.06-7.71-2.71-10.81,2.06-5.21,8.01-12.47,12.24-19.68,16.69-2.31,1.43-4.22.35-6.16-1.11-3.16-2.37-4.07-2.23-6.83.8-.47.51-.92,1.04-1.38,1.55-2.88,3.18-4.38,3.47-7.87,1.54-3.57-1.97-4.36-1.73-6.7,2.06-3.14,5.07-7.1,5.69-10.1.63-3.34-5.63-7.06-5.68-12.07-4.32-7.49,2.04-15.15,3.36-22.8,4.28-2.2.26-4.89-1.43-6.86-3.09-2.97-2.52-5.69-2.48-8.84-.91-2.75,1.37-5.6,2.64-8.5,3.34-1.9.46-3.99-.1-5.97-.36-.76-.1-1.47-.65-2.21-.98-2.64-1.15-5.14-3.51-8-2.22v54.14h428v-21.25c-2.99-1.92-5.99-3.82-8.96-5.79-7.99-5.29-15.92-10.73-23.98-15.86Z"/>
                        </svg>
                    </div>
                </div>

                
            </div>
            <!-- Dashbaord graph -->

            <div class="w-full">
                <div class="w-full flex">
                    <div class="w-2/3">
                        <div class="shadow-md bg-white w-full p-2 rounded-md mt-3">
                            <Chart type="line" :data="lineData"  :height="70" />
                        </div>
                    </div>
                    <div class="w-1/3 ml-3 mt-3">
                        <div class="w-full justify-between flex rounded-md p-3 shadow-md bg-white">
                        
                            <Chart type="doughnut" :data="pieData" :options="pieOptions" :width="158" :height="10" />
                            <div class="justify-end text-end" >
                                <div class="flex"> 
                                    <div class="bg-green-500 border-green-600 border-2 w-14 h-5"></div>
                                    <div class="ml-1">Delivered</div> 
                                </div>
                                <div class="flex"> 
                                    <div class="bg-orange-500 border-orange-600 border-2 w-14 h-5"></div>
                                    <div class="ml-1">Pending</div> 
                                </div>
                                <div class="flex"> 
                                    <div class="bg-blue-500 border-blue-600 border-2 w-14 h-5"></div>
                                    <div class="ml-1">Process</div> 
                                </div>
                                <div class="flex"> 
                                    <div class="bg-yellow-500 border-yellow-600 border-2 w-14 h-5"></div>
                                    <div class="ml-1">Packaging</div> 
                                </div>
                                <div class="flex"> 
                                    <div class="bg-pink-500 border-pink-600 border-2 w-14 h-5"></div>
                                    <div class="ml-1">Cancel</div> 
                                </div>
                                <div class="flex"> 
                                    <div class="bg-red-500 border-red-600 border-2 w-14 h-5"></div>
                                    <div class="ml-1">Rejected</div> 
                                </div>
                            </div>
                        
                        </div>
                    </div>
                </div>
                <div class="flex w-full">
                    <div class="w-2/3 flex">
                        <div class="shadow-md bg-white w-full p-2 rounded-md mt-3">
                            <div class="flex w-full justify-between">
                                <div class="order_title">
                                    <H1 class="text-md font-semibold">Recent Order List</H1>
                                </div>
                                <div class="order_title text-sm">
                                    <div class="pagination">
                                        <a class="p-1  mt-1 text-black " href="#">&laquo;</a>
                                        <a class="p-1 px-2 mt-1 border-t-4 border-red-500 text-red-500" href="#">1</a>
                                        <a class="p-2 mt-1 text-black m-1" href="#">2</a>
                                        <a class="p-2 mt-1 text-black m-1" href="#">3</a>
                                        <a class="p-2 mt-1 text-black m-1" href="#">4</a>
                                        <a class="p-2 mt-1 text-black m-1" href="#">5</a>
                                        <a class="p-2 mt-1 text-black m-1" href="#">...</a>
                                        <a class="p-2 mt-1 text-black m-1" href="#">6</a>
                                        <a class="p-2 mt-1 text-black m-1" href="#">&raquo;</a>
                                    </div>
                                </div>
                                

                            </div>
                                <table class="table-auto w-full mt-2" ref="pdfSection">
                                    <thead >
                                        <tr class="w-full bg-gray-300 text-xs">
                                            <th class="p-1 text-left text-xs">SL</th>
                                            <th class="p-1 text-left text-xs">Name</th>
                                            <th class="p-1 text-left text-xs">Invoice#</th>
                                            <th class="p-1 text-left text-xs">Qty</th>
                                            <th class="p-1 text-left text-xs">Total</th>
                                            <th class="p-1 text-left">Status</th>
                                            <th class="p-1 text-left">Date</th>
                                        </tr>
                                    </thead>
                                    <tbody>
                                        <tr class="bg-white odd:bg-gray-100">
                                            <td class="p-1 text-left text-xs">1</td>
                                            <td class="p-1 text-left text-xs">Md Majadul Islam</td>
                                            <td class="p-1 text-left text-xs">#123456778</td>
                                            <td class="p-1 text-left text-xs">3</td>
                                            <td class="p-1 text-left text-xs">1234</td>
                                            <td class="p-1 text-left text-xs">Pending</td>
                                            <td class="p-1 text-left text-xs">30-nov-2023 10:30</td>
                                            
                                        </tr>
                                        <tr class="bg-white odd:bg-gray-100">
                                            <td class="p-1 text-left text-xs">2</td>
                                            <td class="p-1 text-left text-xs">Md Majadul Islam</td>
                                            <td class="p-1 text-left text-xs">#123456778</td>
                                            <td class="p-1 text-left text-xs">3</td>
                                            <td class="p-1 text-left text-xs">1234</td>
                                            <td class="p-1 text-left text-xs">Pending</td>
                                            <td class="p-1 text-left text-xs">30-nov-2023 10:30</td>
                                            
                                        </tr>
                                        <tr class="bg-white odd:bg-gray-100">
                                            <td class="p-1 text-left text-xs">3</td>
                                            <td class="p-1 text-left text-xs">Md Majadul Islam</td>
                                            <td class="p-1 text-left text-xs">#123456778</td>
                                            <td class="p-1 text-left text-xs">3</td>
                                            <td class="p-1 text-left text-xs">1234</td>
                                            <td class="p-1 text-left text-xs">Pending</td>
                                            <td class="p-1 text-left text-xs">30-nov-2023 10:30</td>
                                            
                                        </tr>
                                        <tr class="bg-white odd:bg-gray-100">
                                            <td class="p-1 text-left text-xs">4</td>
                                            <td class="p-1 text-left text-xs">Md Majadul Islam</td>
                                            <td class="p-1 text-left text-xs">#123456778</td>
                                            <td class="p-1 text-left text-xs">3</td>
                                            <td class="p-1 text-left text-xs">1234</td>
                                            <td class="p-1 text-left text-xs">Pending</td>
                                            <td class="p-1 text-left text-xs">30-nov-2023 10:30</td>
                                            
                                        </tr>
                                        <tr class="bg-white odd:bg-gray-100">
                                            <td class="p-1 text-left text-xs">5</td>
                                            <td class="p-1 text-left text-xs">Md Majadul Islam</td>
                                            <td class="p-1 text-left text-xs">#123456778</td>
                                            <td class="p-1 text-left text-xs">3</td>
                                            <td class="p-1 text-left text-xs">1234</td>
                                            <td class="p-1 text-left text-xs">Pending</td>
                                            <td class="p-1 text-left text-xs">30-nov-2023 10:30</td>
                                            
                                        </tr>
                                        
                                    </tbody>
                            </table>
                        </div>
                    </div>

                    <div class="w-1/3 ml-3">
                        <div class="shadow-md bg-white w-full p-2 rounded-md mt-3">
                            <Chart type="bar" :data="barData"  class="h-30rem"  />
                        </div>

                    </div>
                </div>
                
            </div>
            
        </div>
    </NuxtLayout>
</template>

<style>

    
</style>