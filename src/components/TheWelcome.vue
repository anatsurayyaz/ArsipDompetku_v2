<script setup>
import WelcomeItem from './WelcomeItem.vue'
import DocumentationIcon from './icons/IconDocumentation.vue'
import ToolingIcon from './icons/IconTooling.vue'
import EcosystemIcon from './icons/IconEcosystem.vue'
import CommunityIcon from './icons/IconCommunity.vue'
import SupportIcon from './icons/IconSupport.vue'
</script>

<template>
  <WelcomeItem>
    <template #icon>
      <DocumentationIcon />
    </template>
    <template #heading>Universitaas</template>

    Saya lulus dari
    <a href="https://uin-suka.ac.id/" target="_blank" rel="noopener">Universitas Islam Negeri Sunan Kalijaga Yogyakarta</a>
    dan lulus pada bulan Mei 2024.
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <ToolingIcon />
    </template>
    <template #heading>Jurusan</template>

    Saya lulus dengan gelar
    <a href="https://id.wikipedia.org/wiki/Sarjana_Komputer" target="_blank" rel="noopener">S.Kom</a>, dari jurusan
    <a href="https://campus.quipper.com/majors/id-teknik-informatika" target="_blank" rel="noopener">Teknik Informatika</a>
    .
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <EcosystemIcon />
    </template>
    <template #heading>Organisasi</template>

    Beberapa Organisasi yang saya ikuti semasa kuliah antara lain:
    <a href="https://permikomnas-ri.or.id/" target="_blank" rel="noopener">PERMIKOMNAS</a>,
    <a href="https://www.youtube.com/@hmpstifuinsunankalijaga2883?app=desktop/" target="_blank" rel="noopener">HMPS-TIF</a>, and
    <a href="https://id.wikipedia.org/wiki/Pergerakan_Mahasiswa_Islam_Indonesia/" target="_blank" rel="noopener">PMII</a>.
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <CommunityIcon />
    </template>
    <template #heading>Pengalaman Project</template>

    Saya memiliki beberapa pengalaman tergabung didalam project, salah satunya yaitu saat saya mengikuti program
    <a href="https://grow.google/intl/id_id/bangkit/?tab=machine-learning/" target="_blank" rel="noopener">Bangkit Academy</a>, Saya bersama team mengerjakan proyek bernama
    <a href="https://www.afternic.com/forsale/vitality.ai" target="_blank" rel="noopener"
      >Vitality.AI</a
    >yang dapat mendeteksi kesalahan gerakan saat berolahraga.
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <SupportIcon />
    </template>
    <template #heading>Asal Daerah</template>

    Saya hidup berpindah-pindah. Saya pernah tinggal di
    <a href="https://id.wikipedia.org/wiki/Kota_Yogyakarta" target="_blank" rel="noopener">Yogyakarta</a>,
    <a href="https://id.wikipedia.org/wiki/Kota_Semarang" target="_blank" rel="noopener">Semarang</a>,
    <a href="https://id.wikipedia.org/wiki/Kota_Tangerang" target="_blank" rel="noopener">Tangerang</a>.
    Tetapi Saya lahir dan tumbuh besar di
    <a href="https://id.wikipedia.org/wiki/Kota_Bengkulu" target="_blank" rel="noopener">Bengkulu</a>.
  </WelcomeItem>
</template>
