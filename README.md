# GSoC-22
The final report about my Google summer of Code 2022 contributions at Fossology

##GSoC’21 with FOSSology

![image](https://user-images.githubusercontent.com/66276301/188545938-e734fddc-e722-46e1-bd5e-e9f6c17a76ed.png)

About me 👩‍💻

I am **Samuel Dushimimana**, a final year student in Software Engineering and Embedded Systems at **Rwanda Coding Academy** with 4 years of experience in building full stack applications. I am so grateful to Fossology
mentors for accepting me as the contributor of this Gsoc'22.

My main work during the 12 weeks of project completion was focused on building the Rest APIs and introducing more pages of the UI.

I am going to outline my work in the following lines.
# OVERVIEW

My work during this period has been involved in the following:

i. Fixing bugs and enhancing the existing features in both the backend and the frontend.
ii. Adding new pages into the frontend.
iii. Adding more REST-FULL APIs to the backend.

# 🌏 CONTRIBUTIONS 

##  FEATURE ENHANCEMENT
I fixed the existing problem that could arise while uploading the FILE , VSC or ULR. After submitting the file to the backend the frontend could wait up to 10 adjacent calls checking if the ununpacka and adj2nest agents has completed their role on the uploaded item.

My work here was to merge the requests maded to the backend in that process into one. The frontend needs to make only one request of submitting the file and then the rest of the work is managed on the backend side.

![image](https://user-images.githubusercontent.com/66276301/188787353-ad7e5e8e-5cb6-4a6f-979b-92051b031abd.png)
![image](https://user-images.githubusercontent.com/66276301/188787365-df71a36d-6c67-4020-b2d7-e4342aeda004.png)

Major Pull Requests

- [fix(API): merge multiple upload-api calls into one.#1](https://github.com/fossology/fossology/pull/2287)
- [fix(MULTIPLE-API-CALLS) merge multiple upload-api calls into one #2](https://github.com/fossology/FOSSologyUI/pull/249)


##  FRONTEND 
My major contributions on the frontend side was focused on working with 3 modules GROUPS , FOSSOLOGY MAINTENANCE and LICENSE.

### 1. GROUPS

i. DELETE GROUP PAGE

The delete group page was currently not available at the UI. So my major work here was to create the corresponding UI that would make it possible to select the group and remove it from the list of available groups.

SCREENSHORT

![image](https://user-images.githubusercontent.com/66276301/188789526-a496d990-6fe2-4109-a862-2452fa32a527.png)


ii. MANAGE GROUP USERS PAGE

This page is there for managing the user roles from several groups. The management of users consists of changing their permission in the group , removing some members and adding back removed members from any specific group.


![image](https://user-images.githubusercontent.com/66276301/188790476-2b13ee6b-5d2e-49ff-aa6a-f31dc7f4d991.png)


### 2. MAINTENANCE

The maintenance page is there to help the user request fossology maintenance operations. Such as validating folders , removing specific rwos from the database , removing files and tables etc.

![image](https://user-images.githubusercontent.com/66276301/188791715-3093c956-19fd-448f-a8af-b002443f4b78.png)


Major Pull Requests

- [feat(ui): implementation of mantainance page on the admin section. #1](https://github.com/fossology/FOSSologyUI/pull/232)
- [feat(integration): Integrated the fossology maintenance page. #2](https://github.com/fossology/FOSSologyUI/pull/252)

### 3. LICENSE 

i. IMPORT LICENSE

The page allows the user to upload the license csv file with corresponding delimiter and enclosure properties.

![image](https://user-images.githubusercontent.com/66276301/188792421-a50888cf-48e4-46fd-bd4a-8df3bd99127a.png)

Pull Request : [feat(UI): Import CSV-license file PAGE](https://github.com/fossology/FOSSologyUI/pull/259)

## BACKEND 

The backend tasks were involved with creating the REST-FULL APIs using PHP Slim framework 
for the functionalities whose APIs were not available.

### 1. GROUPS
i.  DELETE GROUP API

There were a need for the REST-API to delete a specific group. This API should receive the group ID and goes on with delete operation of the group.

![image](https://user-images.githubusercontent.com/66276301/188793517-c67f6f36-32a1-49f9-b7a9-1302efb379e1.png)

PR: - [feat(API): delete user group #2](https://github.com/fossology/fossology/pull/2244)

ii. GET DELETABLE GROUPS

Some groups at fossology are there by default and cannot be deleted. The deletable groups are those that were added after the default ones.
Sometimes the user needs to see the Groups which he has a privilege of deleting. The API returns a list of those groups.

![image](https://user-images.githubusercontent.com/66276301/188794792-a8d47911-022b-4021-9086-982bd6b7b434.png)


PR: - [feat(API): list groups that can be deleted](https://github.com/fossology/fossology/pull/2247) 

iii. GET GROUP MEMBERS WITH ROLES

There were a need for the REST API to get all the group members with corresponding roles. The API could be used whlie managing the users on the UI.

![image](https://user-images.githubusercontent.com/66276301/188795223-116dc03e-455a-4ef1-9c47-4f95fc817170.png)

PR: - [feat(API): get group members with corresponding roles](https://github.com/fossology/fossology/pull/2251) 

iv. CHANGE GROUP MEMBER'S PERMISSION

The API changes the permission of the specified user and assigns a new role in the group.

PR: - [feat(API): change group member's permission](https://github.com/fossology/fossology/pull/2259) 

v. ADD USER TO A GROUP

The API adds a user to the group as the new member. If the user is removed from the group , it could be a challenge
when we re-add him back into the group.

![image](https://user-images.githubusercontent.com/66276301/188796265-784755eb-c848-486e-8634-1ef98fc41261.png)

PR: - [feat(API): feat(API): add user to a group. ](https://github.com/fossology/fossology/pull/2303)  


### 2. MAINTENANCE


### 3. LICENSE

1. Added a new Page for Running Fossology Maintenance Operations

