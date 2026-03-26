<script setup>
import { courseData } from "../generated/course-content.mjs"
import CourseMeta from "./CourseMeta.vue"
import CourseMaterialsTable from "./CourseMaterialsTable.vue"
import OutlineSection from "./OutlineSection.vue"
import TeachingTeam from "./TeachingTeam.vue"

const navItems = [
  { href: "#course-info", label: "课程信息" },
  { href: "#teaching-team", label: "任课教师与助教" },
  { href: "#course-materials", label: "课程资料" },
  { href: "#outline-zh", label: "内容简介" },
]
</script>

<template>
  <div class="syllabus-page">
    <aside class="syllabus-sidebar">
      <h1>{{ courseData.course.titleZh }}</h1>
      <p class="syllabus-subtitle">{{ courseData.course.titleEn }}</p>

      <nav class="syllabus-nav">
        <a v-for="item in navItems" :key="item.href" :href="item.href">{{ item.label }}</a>
      </nav>
    </aside>

    <main class="syllabus-main">
      <section id="course-info" class="syllabus-section">
        <h2>课程信息</h2>
        <CourseMeta />
      </section>

      <TeachingTeam />

      <CourseMaterialsTable />

      <OutlineSection
        section-id="outline-zh"
        title="内容简介"
        :modules="courseData.chineseModules"
        core-label="核心思想："
        module-prefix="模块"
      />
    </main>
  </div>
</template>
