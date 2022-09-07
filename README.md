<h1 align="center">Google Summer of Code 2022 <img src="https://media2.giphy.com/media/KB8MHRUq55wjXVwWyl/source.gif" width="50"></h1>

<p align="center"><i>A full report on my Google Summer of Code 2022 work with FOSSology</i></p>
<p align="center"><i>Project: "REST API and UI improvements" </i>  👨‍💻</p>

<p align="center">
        <img src="https://64.media.tumblr.com/c93f16953341ab06acd12b493659bdee/tumblr_mr68hhmVE11r5ikx8o1_400.gif" width="100">
</p>

![Logo](/Assets/GSoC-FOSSology.png)

## Google Summer of Code 2022 🚩 Report: "REST API and UI improvements" 👨‍💻
<!-- 
![ViewCount](https://views.whatilearened.today/views/github/dushimsam/GSoC-2022.svg)
![GitHub](https://img.shields.io/github/followers/dushimsam?style=social)
![Twitter](https://img.shields.io/twitter/follow/dushimsam?style=social)
![GitHub Stars](https://img.shields.io/github/stars/dushimsam/GSoC-2022?style=social) -->

About me 👩‍💻

I am **Samuel Dushimimana**, a graduate in Software Engineering and Embedded Systems at **Rwanda Coding Academy** with 4 years of experience in building full stack applications. I'm grateful to be a part of Fossology community in Google Summer of Code 2022.

In this article am going to outline the details of my contributions as my reference of project completion during the 12 weeks of coding.


# 🌏 CONTRIBUTIONS 

During this period i have been working on different modules of the project in the three categories:

- **EXISITING FEATURE ENHANCEMENT:** In this category i have been fixing existing bugs in the REST end points and introducing new features on the UI to enhance the user experience.

- **UI EMPROVEMENT:** Introducing new pages to the frontend.

- **BUILDING REST APIS:** The formal backend did not expose all the required APIs to satisfy the UI. I raised more than 12 PRs of new APIs to be consumed by the client.

Let's dive into each category in details to showcase all the contributions with the corresponding screenshots where possible and the respective links to the Pull requests.

##  FEATURE ENHANCEMENT

I fixed the existing problem that could arise in uploads such as  FILE , VCS or the ULR type. After submitting the file to the backend for-instance the client could also wait up to 10 adjacent calls checking if the ununpack and adj2nest agents has completed their role on the uploaded item so that it can goes on requesting for the creation of the corresponding job of the item.

Sometimes the 10 adjacent calls were not enough for the agents to having completed the work;as the result the corresponding job for the uploaded item could not be created.

My work here was to merge these processes into one in other words through one upload request from the client; i will do the rest of the work on the backend side. Here the client will not need again to wait so that it can continue with the request of the job creation.

![image](https://user-images.githubusercontent.com/66276301/188787353-ad7e5e8e-5cb6-4a6f-979b-92051b031abd.png)
![image](https://user-images.githubusercontent.com/66276301/188787365-df71a36d-6c67-4020-b2d7-e4342aeda004.png)

**Major Pull Requests**

- [fix(API): merge multiple upload-api calls into one.#1](https://github.com/fossology/fossology/pull/2287)
- [fix(MULTIPLE-API-CALLS) merge multiple upload-api calls into one #2](https://github.com/fossology/FOSSologyUI/pull/249)


##  UI EMPROVEMENT (FRONTEND) 
 
The major contributions on the frontend side in this period was focused on enhancing the 3 modules of the project which are **GROUPS** , **FOSSOLOGY MAINTENANCE** and **LICENSE**.

### 1. GROUPS

**i. DELETE GROUP PAGE**

Created the Delete group page to avail the user to delete a particular group. I developed the page in the REACT Js and the useful components for the page such as the POP-UP modal. This UI work was also proceded by integrating the page to the REST-APIs to make it more dynammic.

![image](https://user-images.githubusercontent.com/66276301/188789526-a496d990-6fe2-4109-a862-2452fa32a527.png)

**Pull request:**-  [feat(ui): added delete group page](https://github.com/fossology/FOSSologyUI/pull/241)

**ii. MANAGE GROUP USERS PAGE**

Created the Page for managing group users. The application admin needs to manage the users in different groups. 
This page needed to meet all these user requirements:

- Admin can add new users to any group as members.
- Admin can view the different existing group and non group members in each group.
- Admin can remove a member from as specific group.
- Admin can change the permission of any member from any group.

My ui-page has satisfied all requirements that were requested.

![image](https://user-images.githubusercontent.com/66276301/188790476-2b13ee6b-5d2e-49ff-aa6a-f31dc7f4d991.png)

**Pull request:**- [feat(UI): added manage group-users page](https://github.com/fossology/FOSSologyUI/pull/248)


### 2. MAINTENANCE

Created the maintenance page to help the user request the running of the fossology maintenance operations. The operations can like validating folders , removing specific rows from the database , removing files and tables etc.
The work involved were to create the UI Page and integrate it to the respective end point.

![image](https://user-images.githubusercontent.com/66276301/188791715-3093c956-19fd-448f-a8af-b002443f4b78.png)


**Major Pull Requests**
- [feat(ui): implementation of mantainance page on the admin section. #1](https://github.com/fossology/FOSSologyUI/pull/232)
- [feat(integration): Integrated the fossology maintenance page. #2](https://github.com/fossology/FOSSologyUI/pull/252)

### 3. LICENSE 

**i. IMPORT LICENSE**

I created the page to help the user to upload any license csv file. The license can be created manually by filling the forms but there was no way through the page to help the user also import existing license files. 

The page i created allows the user to upload the license csv file with corresponding delimiter and enclosure properties. The properties are useful parameters used on the backend to extract significant information from the license file.

![image](https://user-images.githubusercontent.com/66276301/188792421-a50888cf-48e4-46fd-bd4a-8df3bd99127a.png)

Pull Request : [feat(UI): Import CSV-license file PAGE](https://github.com/fossology/FOSSologyUI/pull/259)

## REST-APIS (BACKEND) 

I fixed and created the new REST-APIs on the fossology backend. Some pages on the UI were not integrated due to the absense of the required end-points to be consumed. Others were there but some of them could not work as expected. My work on the backend was to fix and introduce new END-POINTS there. Some of my major modules i focused on to improve were **GROUPS** , **UPLOADS** , **MAINTENANCE** AND **LICENSE**.


### 1. GROUPS

**i. DELETE GROUP API**

I added the delete functionality from the groups module to remove any specific deletable group. This API was required to be consumed by the Delete group page. Through the given **GROUP_ID**__ in the request params, my API can manage the rest of the work.

![image](https://user-images.githubusercontent.com/66276301/188793517-c67f6f36-32a1-49f9-b7a9-1302efb379e1.png)

PR: - [feat(API): delete user group](https://github.com/fossology/fossology/pull/2244)

**ii. GET DELETABLE GROUPS**

I created the end point to return the list of the groups that can be deleted to the calling client. Some groups at fossology are there by default and cannot be deleted. On the delete-group page from the UI needed to know which groups to be listed down which are the ones that are possible to be removed.

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

v. REMOVE MEMBER FROM GROUP

![image](https://user-images.githubusercontent.com/66276301/188797257-b4f33e6f-d964-4c10-9089-51ac2a8f9e9d.png)

PR: - [feat(API): remove member from group](https://github.com/fossology/fossology/pull/2269)

v. ADD USER TO A GROUP

The API adds a user to the group as the new member. If the user is removed from the group , it could be a challenge
when we re-add him back into the group.

![image](https://user-images.githubusercontent.com/66276301/188796265-784755eb-c848-486e-8634-1ef98fc41261.png)

PR: - [feat(API): feat(API): add user to a group. ](https://github.com/fossology/fossology/pull/2303)  


### 2. MAINTENANCE



### 3. LICENSE

1. Added a new Page for Running Fossology Maintenance Operations

