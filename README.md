# docker-volume-clone
clone docker volume

Container Data Cloning
 
IN old VM	
docker run --rm --volumes-from jsreport-server -v $(pwd):/backups ubuntu tar cvf /backups/JS_backup.tar /app/data<volume path>
	 
Move the .tar from old VM to the new VM

In new VM 
docker run --rm --volumes-from jsreport-server -v $(pwd):/backups ubuntu bash -c "cd /app/data && tar xvf /backups/JS_backup.tar --strip 1"
