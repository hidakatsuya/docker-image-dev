FROM mcr.microsoft.com/playwright:focal

WORKDIR /app

RUN npm install @playwright/test
RUN npx playwright install

ENTRYPOINT ["npx", "playwright", "run-server"]
