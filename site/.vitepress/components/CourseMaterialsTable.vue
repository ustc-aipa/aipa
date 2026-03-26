<script setup>
import { withBase } from "vitepress"
import { courseData } from "../generated/course-content.mjs"
</script>

<template>
  <section id="course-materials" class="syllabus-section">
    <h2>课程资料</h2>
    <table class="course-materials-table">
      <thead>
        <tr>
          <th>Week</th>
          <th>Class Material</th>
          <th>Homework</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="week in courseData.materialsWeeks" :key="week.slug">
          <td class="week-cell">{{ week.label }}</td>
          <td>
            <ul v-if="week.classMaterials.length" class="file-list">
              <li v-for="item in week.classMaterials" :key="item.href">
                <a :href="withBase(item.href)" class="file-link" download>{{ item.name }}</a>
              </li>
            </ul>
            <span v-else class="placeholder-text">to be come</span>
          </td>
          <td>
            <ul v-if="week.homework.length" class="file-list">
              <li v-for="item in week.homework" :key="item.href">
                <a :href="withBase(item.href)" class="file-link" download>{{ item.name }}</a>
              </li>
            </ul>
            <span v-else class="placeholder-text">-</span>
          </td>
        </tr>
      </tbody>
    </table>
  </section>
</template>
