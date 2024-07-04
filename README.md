# InviteMe App - Web Application

InviteMe is a event handler [Next.js](https://nextjs.org/) project that i created to learn Next 14 features building a zero runtime application. This application is meant to handle events in slack servers, google calendar, discord or other event platforms, creating roles and groups, descriptions or images on the app.

## How to Run

After pulling this repository, you must pull its submodules (frontend and backend repositories)
Then, run the development docker environment:

```bash
sudo docker compose up
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

## Built with

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-323330?style=for-the-badge&logo=javascript&logoColor=F7DF1E)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![Node.js](https://img.shields.io/badge/Node%20js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![NPM](https://img.shields.io/badge/npm-CB3837?style=for-the-badge&logo=npm&logoColor=white)
![Nest.js](https://img.shields.io/badge/nestjs-E0234E?style=for-the-badge&logo=nestjs)
![React.js](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Next.js](https://img.shields.io/badge/next%20js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)
![Shadcn/UI](https://img.shields.io/badge/SHADCN/UI-444444?style=for-the-badge&logo=shadcnui&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![Prisma ORM](https://img.shields.io/badge/Prisma-3982CE?style=for-the-badge&logo=Prisma&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=JSON%20web%20tokens&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)
![Jest](https://img.shields.io/badge/Jest-C21325?style=for-the-badge&logo=jest&logoColor=white)

## Business Requirement

- Dashboard with avaliable events (house reserved that the logged user is insert on, or public events)  
- Event Administration Page
- Role Based Authorization System on each event  
- Image Repository to handle avatars and thumbnails (Self hosted? S3? not defined yet)  

## Project Requirements

### Back end

- All codebase must be inside this repository
- Dependencies must be defined in a config file inside the repository and containerizable, not on the OS
- Project must be runnable in different environments (development, staging, production)
- Backing services must external services
- Separate build and running stage inside the container  
- Application must be stateless (read only containers, ephemeral)
- Service must be exposed to a bind port
- Scalability must be horizontal (be able to quickly deploy more containers to process requests)
- The whole application must be disposable, in case of invasion, the container must be burned and redeployed
- Development and Production environment must be pared
- Logs must streamed (remember log4j vulnerability)
- Admins processes must no be executed in a isolated container

### Database

- **Relational Database => PostgreSQL** running on a Docker container for development environment, Vercel Postgres DB for deployment environment (why? because it's free).
- Object-Relational Mapping? **Prisma ORM**, good Typescript integration, cascading relations and easy to change entities schemas (will definitely have some changes over time)

### Front End

- Approved on [Core Web Vitals](https://search.google.com/search-console/core-web-vitals?resource_id=sc-domain%3Ainviteme.valmo.dev)
- Approved on [Page Speed Insights](https://pagespeed.web.dev/analysis/https-inviteme-valmo-dev/vf7h47cofj?form_factor=desktop)
- Full customization on event/groups color and thumbnail with drag and drop images
- Zero Runtime UI Libraries, if we are going to use Next.js as framework, there is not sense in using CSS in JS or other stying solutions that will generate some runtime to generate the CSS, soo **Tailwind CSS and Shadcn/UI** will be used for stying
- Being able to organize the groups and roles by drag and dropping  
