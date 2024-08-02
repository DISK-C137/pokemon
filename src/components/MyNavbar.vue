<template>
    <nav class="bg-gray-800 p-4">
        <div class="container mx-auto flex justify-between items-center">
            <!-- ชื่อของเว็บไซต์หรือแอปพลิเคชัน -->
            <div class="text-white text-lg font-semibold">
                Pokémon List
            </div>
            <!-- กล่องค้นหา -->
            <div class="relative">
                <ul class="flex items-center space-x-4">
                    <li>
                        <!-- ป้ายกำกับสำหรับกล่องค้นหา -->
                        <label for="searchInput" class="text-white">Search</label>
                        <!-- กล่องค้นหา -->
                        <!-- ผูกค่าการค้นหากับ state ของคอมโพเนนต์ -->
                        <!-- เรียกใช้ฟังก์ชัน onSearch เมื่อมีการพิมพ์ -->
                        <input type="text" id="searchInput" v-model="searchTerm" @input="onSearch"
                            class="ml-2 px-4 py-2 rounded-lg bg-gray-700 text-white border border-gray-600 focus:outline-none focus:ring-2 focus:ring-blue-500"
                            placeholder="Search Pokémon" /><!-- ข้อความแสดงตัวอย่างในกล่องค้นหา -->
                    </li>
                </ul>
            </div>
        </div>
    </nav>
</template>

<script>
export default {
    data() {
        return {
            searchTerm: '' // กำหนดค่าเริ่มต้นเป็นค่าว่างสำหรับเก็บข้อมูลการค้นหา
        };
    },
    methods: {
        onSearch() {
            // ส่งค่าการค้นหาไปยังคอมโพเนนต์หลักผ่าน event emitter
            this.$emit('search', this.searchTerm);
        }
    }
}
</script>

<style scoped></style>
