<template>
<div class="question">
    <h3>Question No.2</h3>
    <label for="family">
        Masukan Jumlah Keluarga
    </label><br>
    <input type="number" name="family" v-model="family" />
    <div v-if="family.length > 0">
        <label for="member">
            Masukan Jumlah Anggota Keluarga, Total Keluarga {{ family }}
        </label><br>
        <input type="text" name="member" v-model="member" />
        <br>
        <div v-if="member.length > 0">
            <div v-if="member_to_array.length == family">
                <div v-for="(data, i ) in member_to_array" :key="i">
                    <p>Jumlah Anggota Keluarga {{ i+1 }} : {{ data }} Orang</p>
                </div>
                Total Jumlah Anggota Keluarga yang ikut : {{ minimum_bus }}<br>
                Minimun Bus Required : {{ Math.ceil(minimum_bus / 4) }}
            </div>
            <div v-else>
                Input must be equal with count of family
            </div>
        </div>
    </div>
</div>
</template>

<script>
export default {
    data() {
        return {
            family: '',
            member: '',
            memberArray: [],
        }
    },
    computed: {
        count_member() {
            return this.member_to_array()
        },
        member_to_array() {
            return this.member.split(' ');
        },
        minimum_bus() {
            let numOr0 = n => isNaN(n) ? 0 : n
            return this.member_to_array.reduce((a, b) => Number(numOr0(a)) + Number(numOr0(b)))
        },
    },
    methods: {
    }
}
</script>
