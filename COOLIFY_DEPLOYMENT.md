# Coolify Deployment Guide for send2ereader

## Prerequisites
- Coolify installed on server `root@31.97.70.110`
- Domain `send.mnd.vn` configured to point to your server

## Deployment Steps

### 1. Connect to Coolify Dashboard
Access your Coolify dashboard (usually at `http://your-server-ip:8000` or your configured domain)

### 2. Create New Application
1. Click "New Application" or "+" button
2. Choose "Docker Compose" or "Dockerfile" deployment method
3. Select "Git Repository" as source

### 3. Repository Configuration
- **Repository URL**: Your Git repository URL (GitHub, GitLab, etc.)
- **Branch**: `master` or `main`
- **Dockerfile Path**: `./Dockerfile`
- **Docker Compose Path**: `./docker-compose.yaml` (if using Docker Compose)

### 4. Environment Variables
Add these environment variables in Coolify:
- `NODE_ENV=production`
- `PORT=3001`

### 5. Domain Configuration
- **Domain**: `send.mnd.vn`
- **SSL**: Enable automatic SSL certificate (Let's Encrypt)
- **Force HTTPS**: Enable

### 6. Port Configuration
- **Internal Port**: `3001`
- **External Port**: `80` (HTTP) and `443` (HTTPS)

### 7. Resource Limits (Optional)
- **Memory**: 512MB - 1GB
- **CPU**: 0.5 - 1 core

### 8. Deploy
Click "Deploy" and wait for the build process to complete.

## Post-Deployment

### Verify Deployment
1. Visit `https://send.mnd.vn` to ensure the application is running
2. Test file upload functionality
3. Check logs in Coolify dashboard for any errors

### Monitoring
- Monitor application logs in Coolify dashboard
- Set up health checks if needed
- Monitor resource usage

## Troubleshooting

### Common Issues
1. **Build fails**: Check Dockerfile and dependencies
2. **Port conflicts**: Ensure port 3001 is available
3. **Domain not working**: Verify DNS settings and SSL certificate
4. **File upload issues**: Check uploads directory permissions

### Logs
Check application logs in Coolify dashboard under "Logs" section.

## Application Features
- Upload ebooks (EPUB, MOBI, PDF, etc.)
- Convert EPUB to MOBI for Kindle devices
- Convert EPUB to KEPUB for Kobo devices
- PDF margin cropping
- Automatic file cleanup after 30 seconds
- Mobile-friendly interface
