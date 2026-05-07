# BrainBytes AI Tutoring Platform

## Project Overview
BrainBytes is an AI-powered tutoring platform designed to provide accessible academic assistance to Filipino students. This project implements the platform using modern DevOps practices and containerization.

## Team Members
- Danilo Giltendez - Team Lead - lr.dgiltendez@mmdc.mcl.edu.ph
- John Paul Arquita - Backend Developer - lr.jparquita@mmdc.mcl.edu.ph
- Kenneth Ian Lu - Frontend Developer - lr.kilu@mmdc.mcl.edu.ph
- Christian John Batuigas - Frontend Developer - lr.cjbatuigas@mmdc.mcl.edu.ph
- Laiza Veronica Llanto - DevOps Engineer - lr.lvllanto@mmdc.mcl.edu.ph


## Project Goals
- Implement a containerized application with proper networking
- Create an automated CI/CD pipeline using GitHub Actions
- Deploy the application to Oracle Cloud Free Tier
- Set up monitoring and observability tools

## Technology Stack
- Frontend: Next.js
- Backend: Node.js
- Database: MongoDB Atlas
- Containerization: Docker
- CI/CD: GitHub Actions
- Cloud Provider: Oracle Cloud Free Tier
- Monitoring: Prometheus & Grafana

## Development Environment Setup Verification

| Team Member             | Docker Installed  | Git Installed | VS Code Installed | Can Run Hello World Container |
|-------------------------|-------------------|---------------|-------------------|-------------------------------|
| Danilo Giltendez        | ✓                 | ✓             | ✓                 | ✓                             |
| John Paul Arquita       | ✓                 | ✓             | ✓                 | ✓                             |
| Kenneth Ian Lu          | ✓                 | x             | ✓                 | ✓                             |
| Christian John Batuigas | x                 | x             | ✓                 | x                             |
| Laiza Veronica Llanto   | ✓                 | ✓             | ✓                 | ✓                             |

## Docker Version Information
Docker version 29.4.2, build 055a478

## Project Architecture Draft

                   BrainBytes Application Architecture  
┌────────────────────────────────────────────────────┐  

                        ┌──────────────────────┐
                        │     User Browser     │
                        │  Client / Web User   │
                        └──────────┬───────────┘
                                   │
                          HTTP Requests (HTTPS)
                                   │
                                   ▼
        ┌─────────────────────────────────────────────────┐
        │            Frontend Container                   │
        │-------------------------------------------------│
        │ Container Name: brainbytes-frontend             │
        │ Technology: Next.js                             │
        │ Port Mapping: 3000:3000                         │
        │ Purpose: User Interface / Chat Interface        │
        └──────────────────┬──────────────────────────────┘
                           │
                           │ REST API Calls / JSON
                           ▼
        ┌─────────────────────────────────────────────────┐
        │             Backend Container                   │
        │-------------------------------------------------│
        │ Container Name: brainbytes-backend              │
        │ Technology: Node.js + Express                   │
        │ Port Mapping: 5000:5000                         │
        │ Purpose: API, Authentication, AI Processing     │
        └───────────────┬─────────────────┬───────────────┘
                        │                 │
                        │                 │
            Database Queries      AI API Requests
              MongoDB URI         AI Model Integration
                        │                 │
                        ▼                 ▼

     ┌────────────────────────┐   ┌────────────────────────┐
     │     MongoDB Atlas      │   │     AI Service/API     │
     │------------------------│   │------------------------│
     │ Cloud Database Storage │   │ OpenAI / AI Model      │
     │ Stores Users, Chats,   │   │ Generates AI Responses │
     │ Message History        │   │ for BrainBytes Chat    │
     └────────────────────────┘   └────────────────────────┘


───────────────────────────────────────────────────────  
Container Communication Flow  

1. User sends request from Browser
2. Next.js Frontend receives request
3. Frontend calls Backend API
4. Backend processes request
5. Backend communicates with:  
      • MongoDB Atlas for data storage  
      • AI Service for AI-generated responses  
6. Response returns to Frontend
7. Frontend displays result to User

───────────────────────────────────────────────────────  
Docker & DevOps Components  

• Docker → Containerized environments  
• Docker Compose → Multi-container orchestration  
• GitHub Actions → CI/CD automation  
• Oracle Cloud → Deployment hosting  
• Prometheus + Grafana → Monitoring & dashboards  

└──────────────────────────────────────────────────────┘  

# Milestone 1 Task Distribution

## Week 1: Container Basics
**Laiza Veronica Llanto**: Set up project repository and basic documentation  
**Danilo Giltendez, Christian John Batuigas**: Research and document containerization approach  
**All Team Members**: Complete Docker installation and verification  

## Week 2: Platform Development
**Christian John Batuigas, Kenneth Ian Lu**: Implement frontend container (Next.js)  
**John Paul Arquita, Danilo Giltendez**: Implement backend container (Node.js)  
**Laiza Veronica Llanto**: Configure MongoDB Atlas and connection  

## Week 3: Platform Development
**Kenneth Ian Lu, Christian John Batuigas**: Implement chat interface frontend  
**John Paul Arquita**: Implement backend API endpoints  
**Laiza Veronica Llanto**: Set up container networking  

## Week 4: Integration and Testing
**John Paul Arquita, Laiza Veronica Llanto**: Integrate AI model  
**Kenneth Ian Lu, Christian John Batuigas**: Implement message history storage  
**Laiza Veronica Llanto, Danilo Giltendez**: Create project documentation  
**All Team Members**: Final testing and preparation for submission
