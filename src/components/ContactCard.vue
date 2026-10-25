<script>
export default {
    props: {
        contact: { type: Object, required: true },
    },
};
</script>

<template>
    <div>
        <div class="p-1"><strong>Tên:</strong> {{ contact.name }}</div>
        <div class="p-1"><strong>E-mail:</strong> {{ contact.email }}</div>
        <div class="p-1"><strong>Địa chỉ:</strong> {{ contact.address }}</div>
        <div class="p-1"><strong>Điện thoại:</strong> {{ contact.phone }}</div>
        <div class="p-1">
            <strong>Liên hệ yêu thích:&nbsp;</strong>
            <i v-if="contact.favorite" class="fas fa-check"></i>
            <i v-else class="fas fa-times"></i>
        </div>

        <!-- THÊM MỚI: hiển thị các sở thích đã chọn (chỉ hiện khi có dữ liệu) -->
        <div class="p-1" v-if="contact.interests && contact.interests.length">
            <strong>Sở thích:&nbsp;</strong>
            <span
                v-for="item in contact.interests"
                :key="item"
                class="badge badge-info mr-1"
            >
                {{ item }}
            </span>
        </div>
    </div>
</template>