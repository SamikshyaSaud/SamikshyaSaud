Lab1 Scenario: Directory and File Management
1. Create a New Directory:
- Navigate to your home directory
cd ~
- Create a directory named project
mkdir project
- Navigate into the project directory
cd project

2. Create Subdirectories:
- Create two subdirectories named docs and src
mkdir docs src

3. Create Files in docs Directory:
- Navigate into the docs directory
cd docs
- Create an empty file named README.md
touch README.md
- Create an empty file named LICENSE
touch LICENSE
- List the files to confirm they are created
ls

4. Copy Files:
- Copy README.md to the src directory
cp README.md ../src/
- Navigate to the src directory to confirm the file was copied and list the contents
cd ../src
ls

5. Move (Rename) Files:
- Rename README.md in the src directory to INTRO.md
mv README.md INTRO.md
- Confirm the file was renamed by listing the directory contents
ls

6. Remove Files:
- Remove the LICENSE file from the docs directory
rm ../docs/LICENSE
- Navigate to the docs directory and confirm the file was removed by listing the contents
cd ../docs
ls

7. Remove Directories:
- Navigate to the parent project directory
cd ..
- Remove the docs directory and its contents
rm -r docs
- Confirm the directory was removed by listing the contents of the parent directory
ls


Lab2 Scenario: Navigating Your Project Directory Tree
1. Create a Directory Tree:
- Navigate to your home directory
cd ~
- Create a directory named project
mkdir project
- Navigate into the project directory
cd project
- Create subdirectories named docs and src
mkdir docs src
- Inside docs, create another directory named guides
mkdir docs/guides
- Inside src, create a directory named scripts
mkdir src/scripts

2. Navigating the Directory Tree Using Relative Paths:
- From the project directory, navigate into the docs directory
cd docs
- From docs, navigate into the guides directory
cd guides
- From guides, navigate back to the docs directory
cd ..
- From docs, navigate up to the project directory
cd ..
- From project, navigate into the src directory
cd src
- From src, navigate into the scripts directory
cd scripts

3. Using Absolute Paths:
- Navigate to the guides directory using the absolute path from your home directory
cd ~/project/docs/guides
- Navigate to the scripts directory using the absolute path from your home directory
cd ~/project/src/scripts

4. Using cd Shortcuts:
- From any directory, navigate to your home directory
cd ~
- From your home directory, navigate back to the last directory you were in
cd -
- From the scripts directory, navigate one level up to the src directory
cd ..
- While in the src directory, navigate to the current directory (no change)
cd .
- From any directory, navigate to the root directory of the file system
cd /


Lab3 Scenario: Command Help and Shell Information
1. Getting Command Help:
- Find out the options and usage of the ls command
ls --help
- Display a brief description of the cp command
whatis cp
- Access the manual pages for the mv command to understand its usage
man mv
- Get a one-line description of the rm command
whatis rm

2. Getting Information About the Current Shell:
- Display the current terminal device name
tty
- Find out which shell you are currently using
echo $SHELL
- Display the username of the currently logged-in user
whoami

3. Checking Running Processes:
- List all currently running processes
ps aux
- Display detailed information about a specific process (e.g., PID 1234)
ps -p 1234 -f
- Find the processes running by the current user
ps -u $(whoami)

4. Extra Information:
- Display the current date and time
date
- Find out how long the system has been running
uptime
- See a list of users currently logged into the system
who


Lab4 Scenario: User and Group Management
1. User Information:
- Display detailed information about a specific user (e.g., user1)
id user1
- List all users on the system
cat /etc/passwd

2. Group Information:
- Display detailed information about a specific group (e.g., group1)
getent group group1
- List all groups on the system
cat /etc/group

3. User Creation:
- Create a new user named student1 with a home directory
sudo useradd -m student1
- Specify a different shell for the new user student1 during creation
sudo useradd -m -s /bin/bash student1

4. Group Creation:
- Create a new group named students
sudo groupadd students

5. Adding User to Group:
- Add the user student1 to the group students
sudo usermod -aG students student1

6. Group Modification:
- Change the group name from students to learners
sudo groupmod -n learners students
- Add a user to multiple groups 
sudo usermod -aG group1,group2 student1

7. Password Policy Setting:
- Set a password for the user student1
sudo passwd student1
- Enforce password expiration for the user student1
sudo chage -M 30 student1

8. Modifying User Shell:
- Change the login shell for the user student1 to /bin/bash
sudo usermod -s /bin/bash student1

9. Modifying User Home Directory:
- Change the home directory of student1 to /home/newstudent1
sudo usermod -d /home/newstudent1 -m student1

10. Removing User:
- Remove the user student1 from the system
sudo userdel -r student1

11. Removing Group:
- Remove the group learners from the system
sudo groupdel learners


Lab5 Scenario: Special Permissions and Shared Folder Collaboration
1. Create the Shared Directory:
- Create a directory named /shared
sudo mkdir /shared

2. Set Group Ownership:
- Create a group named collab
sudo groupadd collab
- Add users to the collab group
sudo usermod -aG collab alice
sudo usermod -aG collab bob
sudo usermod -aG collab carol
- Change the group ownership of the shared directory
sudo chown :collab /shared

3. Set Directory Permissions:
- Grant appropriate permissions to the group
sudo chmod 770 /shared
- Set the setgid bit on the shared directory
sudo chmod g+s /shared

4. Configure Umask for User Collaboration:
- Set the umask value for users to ensure files are created with appropriate default permissions
umask 002

5. Set Sticky Bit on the Shared Directory:
- Set the sticky bit on the shared directory
sudo chmod +t /shared

6. Testing Permissions and Collaboration:
- Log in as alice and create a file in /shared
su - alice
touch /shared/alice_file.txt
- Log in as bob and create another file in /shared
su - bob
touch /shared/bob_file.txt
- Check the ownership and permissions of files in /shared
ls -l /shared
- As alice, attempt to delete bob_file.txt
su - alice
rm /shared/bob_file.txt
- As bob, attempt to delete alice_file.txt
su - bob
rm /shared/alice_file.txt

7. Review and Summary:
-Verify that new files inherit the group ownership.
ls -l /shared
-Ensure that the umask value is configured correctly for the desired default permissions.
umask
-Confirm that the sticky bit is functioning as expected by testing file deletion.
ls -l /shared
