# 👋 Hello, I'm Sai Divya!

Welcome to my GitHub profile! I am an experienced **Python Developer & Full-Stack Engineer** with 8+ years of professional expertise. I’m passionate about building scalable applications, designing data-driven solutions, and integrating machine learning into production systems.

![Profile Views](https://komarev.com/ghpvc/?username=sai-divya-adapa&color=brightgreen)

---

## 🌟 Academic Background

- 🎓 **Master of Science in Computer Science**  
  *University of North Texas | Aug 2023 - May 2025*  
- 🎓 **Bachelor of Engineering in Electronics and Communications Engineering**  
  *Andhra Loyola Institute of Technology & Sciences | 2014 - 2017*  
- 🌐 Visit my [Portfolio](#) for more about my work!  

---

## 🌐 Connect with Me  

[![LinkedIn](https://img.shields.io/badge/-LinkedIn-blue?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/adapadivya/)  
[![GitHub](https://img.shields.io/badge/-GitHub-lightgrey?style=flat&logo=github&logoColor=white)](https://github.com/SaiDivyaAdapa/Sai-Divya-Adapa-Portfolio)  
[![Email](https://img.shields.io/badge/-Email-red?style=flat&logo=gmail&logoColor=white)](mailto:divyasai3195@gmail.com)  

---

## 🛠️ Skills  

### Programming & Tools  
![Python](https://img.shields.io/badge/-Python-blue?style=flat-square&logo=python&logoColor=white)
![JavaScript](https://img.shields.io/badge/-JavaScript-yellow?style=flat-square&logo=javascript&logoColor=black)
![React](https://img.shields.io/badge/-React-blue?style=flat-square&logo=react&logoColor=white)
![Django](https://img.shields.io/badge/-Django-darkgreen?style=flat-square&logo=django&logoColor=white)
![Flask](https://img.shields.io/badge/-Flask-black?style=flat-square&logo=flask&logoColor=white)
![FastAPI](https://img.shields.io/badge/-FastAPI-teal?style=flat-square&logo=fastapi&logoColor=white)
![SQL](https://img.shields.io/badge/-SQL-blue?style=flat-square&logo=postgresql&logoColor=white)
![MongoDB](https://img.shields.io/badge/-MongoDB-green?style=flat-square&logo=mongodb&logoColor=white)
![Docker](https://img.shields.io/badge/-Docker-blue?style=flat-square&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/-Kubernetes-darkblue?style=flat-square&logo=kubernetes&logoColor=white)
![AWS](https://img.shields.io/badge/-AWS-orange?style=flat-square&logo=amazon-aws&logoColor=white)
![Tableau](https://img.shields.io/badge/-Tableau-blue?style=flat-square&logo=tableau&logoColor=white)
![Power BI](https://img.shields.io/badge/-Power%20BI-yellow?style=flat-square&logo=power-bi&logoColor=black)

### Key Areas of Expertise  
- Full-Stack Development (React, Django, Flask, FastAPI)  
- RESTful API & Microservices Architecture  
- Data Engineering & ETL Pipelines  
- Machine Learning (scikit-learn, TensorFlow, PyTorch)  
- Cloud Deployment (AWS, GCP, Azure)  
- DevOps & CI/CD (Docker, Kubernetes, Jenkins, GitHub Actions)  
- Data Visualization (Tableau, Power BI, Plotly, Seaborn)  

---

// SkillPieChart — React component (single-file) to show programming skills as a pie chart
// Usage:
// 1) Install Recharts: `npm install recharts`
// 2) Make sure Tailwind CSS is set up in your project (or adapt classes to plain CSS)
// 3) Import and use: `import SkillPieChart from './portfolio-skill-piechart.jsx'`
//    <SkillPieChart data={[{name: 'Python', value: 40}, {name: 'JavaScript', value: 30}, ...]} />

import React from 'react'
import {
  PieChart,
  Pie,
  Cell,
  Tooltip,
  Legend,
  ResponsiveContainer,
} from 'recharts'

const DEFAULT_COLORS = [
  '#4F46E5', // indigo
  '#06B6D4', // cyan
  '#F97316', // orange
  '#10B981', // green
  '#EF4444', // red
  '#8B5CF6', // violet
  '#F59E0B', // amber
]

export default function SkillPieChart({
  data = [
    { name: 'Python', value: 40 },
    { name: 'JavaScript', value: 25 },
    { name: 'SQL', value: 15 },
    { name: 'DevOps', value: 10 },
    { name: 'Other', value: 10 },
  ],
  title = 'Programming Skills',
  colors = DEFAULT_COLORS,
}) {
  // Normalize values so they sum to 100 if they don't already
  const total = data.reduce((s, d) => s + (d.value || 0), 0) || 1
  const normalized = data.map((d) => ({ ...d, value: (d.value / total) * 100 }))

  return (
    <div className="w-full max-w-xl mx-auto p-4 bg-white dark:bg-gray-900 rounded-2xl shadow-md">
      <div className="flex items-center justify-between mb-4">
        <h3 className="text-lg font-semibold text-gray-900 dark:text-gray-100">{title}</h3>
        <div className="text-sm text-gray-500 dark:text-gray-300">Visualized as percentage</div>
      </div>

      <div style={{ width: '100%', height: 300 }}>
        <ResponsiveContainer>
          <PieChart>
            <Pie
              data={normalized}
              dataKey="value"
              nameKey="name"
              innerRadius={60}
              outerRadius={100}
              paddingAngle={3}
              label={({ name, percent }) => `${name}: ${Math.round(percent * 100)}%`}
            >
              {normalized.map((entry, index) => (
                <Cell key={`cell-${index}`} fill={colors[index % colors.length]} />
              ))}
            </Pie>
            <Tooltip formatter={(value) => `${value.toFixed(1)}%`} />
            <Legend verticalAlign="bottom" height={36} />
          </PieChart>
        </ResponsiveContainer>
      </div>

      <div className="mt-4 text-sm text-gray-600 dark:text-gray-300">
        Tip: Pass your real skill values to the <code>data</code> prop. Values can be relative (e.g., 4, 3, 2) — the component will normalize them.
      </div>
    </div>
  )
}

