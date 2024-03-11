# Các bước config 
1. Backend
    ```
   cd backend
   cp .env.example .env (Sửa các config DB giống environment trong docker-compose.yml)
   chmod -R 777 storage
   ```
2. Chạy Docker
    ```
    docker-compose build
    docker-compose up -d
    ```
3. Chạy data để test
    ```
    docker-compose exec app php artisan migrate
    docker-compose exec app php artisan db:seed
    ```
4. Link  
BE: http://0.0.0.0:8000/  
FE: http://0.0.0.0:3000/