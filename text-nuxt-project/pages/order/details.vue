<template>
    <NuxtLayout :name="layout">
        <div class="max-w-5xl mx-auto p-8 bg-white rounded border-2 shadow-md my-6 mt-2" id="invoice">
            <!-- Client info -->
            <div class="grid grid-cols-2 items-center mt-8">
                <div>
                    <p class="font-bold text-gray-800">
                        Bill to :
                    </p>
                    <p class="text-gray-500">
                        Md Majadul Islam
                        <br />
                        110/1, Mirpur-11, Dhaka
                    </p>
                    <p class="text-gray-500">
                        info@Majadul.com
                    </p>
                </div>

                <div class="text-right">
                    <p class="">
                        Invoice number:
                        <span class="text-gray-500">INV-2023786123</span>
                    </p>
                    <p>
                        Invoice date: <span class="text-gray-500">03/07/2023</span>
                        <br />
                        Due date:<span class="text-gray-500">31/07/2023</span>
                    </p>
                </div>
            </div>

            <!-- Invoice Items -->
            <div class="-mx-4 mt-8 flow-root sm:mx-0">
                <table class="min-w-full">
                    <colgroup>
                        <col class="sm:w-1/12">
                        <col class="sm:w-1/12">
                        <col class="sm:w-1/12">
                        <col class="sm:w-1/12">
                        <col class="sm:w-1/12">
                        <col class="sm:w-1/12">
                        <col class="sm:w-1/12">
                    </colgroup>
                    <thead class="border-b border-gray-400 bg-gray-100 text-gray-900 ">
                        <tr>
                            <th scope="col"
                                class="py-3.5 pl-4 pr-3 text-left text-sm font-semibold text-gray-900 sm:pl-0">User
                            </th>
                            <th scope="col"
                                class="py-3.5 pl-4 pr-3 text-left text-sm font-semibold text-gray-900 sm:pl-0">Items
                            </th>
                            <th scope="col"
                                class="hidden px-3 py-3.5 text-right text-sm font-semibold text-gray-900 sm:table-cell">
                                Contact</th>
                            <th scope="col"
                                class="hidden px-3 py-3.5 text-right text-sm font-semibold text-gray-900 sm:table-cell">
                                OrderID</th>
                            <th scope="col"
                                class="hidden px-3 py-3.5 text-right text-sm font-semibold text-gray-900 sm:table-cell">
                                Quantity</th>
                            <th scope="col"
                                class="hidden px-3 py-3.5 text-right text-sm font-semibold text-gray-900 sm:table-cell">
                                Price</th>
                            <th scope="col"
                                class="py-3.5 pl-3 pr-4 text-right text-sm font-semibold text-gray-900 sm:pr-0">Amount
                            </th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr class="border-b border-gray-200">
                            <td class="py-5 text-left text-sm text-gray-500 sm:table-cell">Md Majedul</td>
                            <td class="max-w-0 py-5 pl-4 pr-3 text-sm sm:pl-0">
                                <div class="font-medium text-gray-900">Premium Black Watch</div>
                            </td>
                            <td class="hidden px-3 py-5 text-right text-sm text-gray-500 sm:table-cell">+88017123465</td>
                            <td class="hidden px-3 py-5 text-right text-sm text-gray-500 sm:table-cell">#1688272740</td>
                            <td class="hidden px-3 py-5 text-right text-sm text-gray-500 sm:table-cell">7.0</td>
                            <td class="hidden px-3 py-5 text-right text-sm text-gray-500 sm:table-cell">$100.00</td>
                            <td class="py-5 pl-3 pr-4 text-right text-sm text-gray-500 sm:pr-0">$700.00</td>
                        </tr>
                        <tr class="border-b border-gray-200">
                            <td class="py-5 text-left text-sm text-gray-500 sm:table-cell">Md Majedul</td>
                            <td class="max-w-0 py-5 pl-4 pr-3 text-sm sm:pl-0">
                                <div class="font-medium text-gray-900">Mack Book 2.0</div>
                            </td>
                            <td class="hidden px-3 py-5 text-right text-sm text-gray-500 sm:table-cell">+88017123465</td>
                            <td class="hidden px-3 py-5 text-right text-sm text-gray-500 sm:table-cell">#1688272740</td>
                            <td class="hidden px-3 py-5 text-right text-sm text-gray-500 sm:table-cell">7.0</td>
                            <td class="hidden px-3 py-5 text-right text-sm text-gray-500 sm:table-cell">$100.00</td>
                            <td class="py-5 pl-3 pr-4 text-right text-sm text-gray-500 sm:pr-0">$700.00</td>
                        </tr>
                        <tr class="border-b border-gray-200">
                            <td class="py-5 text-left text-sm text-gray-500 sm:table-cell">Md Majedul</td>
                            <td class="max-w-0 py-5 pl-4 pr-3 text-sm sm:pl-0">
                                <div class="font-medium text-gray-900">Hot Gold bar</div>
                            </td>
                            <td class="hidden px-3 py-5 text-right text-sm text-gray-500 sm:table-cell">+88017123465</td>
                            <td class="hidden px-3 py-5 text-right text-sm text-gray-500 sm:table-cell">#1688272740</td>
                            <td class="hidden px-3 py-5 text-right text-sm text-gray-500 sm:table-cell">7.0</td>
                            <td class="hidden px-3 py-5 text-right text-sm text-gray-500 sm:table-cell">$100.00</td>
                            <td class="py-5 pl-3 pr-4 text-right text-sm text-gray-500 sm:pr-0">$700.00</td>
                        </tr>
                    </tbody>
                    <tfoot>
                        <tr>
                            <th scope="row" colspan="3"
                                class="hidden pl-4 pr-3 pt-6 text-right text-sm font-normal text-gray-500 sm:table-cell sm:pl-0">
                                Subtotal
                            </th>
                            <th scope="row"
                                class="pl-6 pr-3 pt-6 text-left text-sm font-normal text-gray-500 sm:hidden">Subtotal
                            </th>
                            <td class="pl-3 pr-6 pt-6 text-right text-sm text-gray-500 sm:pr-0">$1,500.00</td>
                        </tr>
                        <tr>
                            <th scope="row" colspan="3"
                                class="hidden pl-4 pr-3 pt-4 text-right text-sm font-normal text-gray-500 sm:table-cell sm:pl-0">
                                Tax</th>
                            <th scope="row"
                                class="pl-6 pr-3 pt-4 text-left text-sm font-normal text-gray-500 sm:hidden">Tax</th>
                            <td class="pl-3 pr-6 pt-4 text-right text-sm text-gray-500 sm:pr-0">$1,50.00</td>
                        </tr>
                        <tr>
                            <th scope="row" colspan="3"
                                class="hidden pl-4 pr-3 pt-4 text-right text-sm font-normal text-gray-500 sm:table-cell sm:pl-0">
                                Discount
                            </th>
                            <th scope="row"
                                class="pl-6 pr-3 pt-4 text-left text-sm font-normal text-gray-500 sm:hidden">Discount
                            </th>
                            <td class="pl-3 pr-6 pt-4 text-right text-sm text-gray-500 sm:pr-0">- 10%</td>
                        </tr>
                        <tr>
                            <th scope="row" colspan="3"
                                class="hidden pl-4 pr-3 pt-4 text-right text-sm font-semibold text-gray-900 sm:table-cell sm:pl-0">
                                Total
                            </th>
                            <th scope="row"
                                class="pl-6 pr-3 pt-4 text-left text-sm font-semibold text-gray-900 sm:hidden">Total
                            </th>
                            <td class="pl-3 pr-4 pt-4 text-right text-sm font-semibold text-gray-900 sm:pr-0">$1,650.00
                            </td>
                        </tr>
                    </tfoot>
                </table>
            </div>

            <!--  Footer  -->
            <div class="border-t-2 pt-4 text-xs text-gray-500 text-center mt-16">
                Please pay the invoice before the due date. You can pay the invoice by logging in to your account from
                our client
                portal.
            </div>

        </div>

        <div class="flex justify-center">
            <button type="button" class="bg-red-800 text-white py-2 px-4 mb-6 rounded-sm">Print</button>
        </div>
    </NuxtLayout>
</template>

<script setup lang="ts">
definePageMeta({
    layout: "dashboard",
})
</script>

<style scoped></style>