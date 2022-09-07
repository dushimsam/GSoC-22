<h1 align="center">Google Summer of Code 2022 <img src="https://media2.giphy.com/media/KB8MHRUq55wjXVwWyl/source.gif" width="50"></h1>

<p align="center"><i>A full report on my Google Summer of Code 2022 work with FOSSology</i></p>
<p align="center"><i>Project: "REST API and UI improvements" </i>  👨‍💻</p>

<p align="center">
        <img src="https://64.media.tumblr.com/c93f16953341ab06acd12b493659bdee/tumblr_mr68hhmVE11r5ikx8o1_400.gif" width="100">
</p>

![image](https://user-images.githubusercontent.com/66276301/188962690-5869b53c-99bb-4012-b13f-443832568f7e.png)

## Google Summer of Code 2022 🚩 Report: "REST API and UI improvements" 👨‍💻
<!-- 
![ViewCount](https://views.whatilearened.today/views/github/dushimsam/GSoC-2022.svg)
![GitHub](https://img.shields.io/github/followers/dushimsam?style=social)
![Twitter](https://img.shields.io/twitter/follow/dushimsam?style=social)
![GitHub Stars](https://img.shields.io/github/stars/dushimsam/GSoC-2022?style=social) -->

About me 👩‍💻

I am **Samuel Dushimimana**, a graduate in Software Engineering and Embedded Systems at **Rwanda Coding Academy** with 4 years of experience in building full stack applications. I'm so excited to be a part of FOSSology community in Google Summer of Code 2022.

In this article am going to outline the details of my contributions as a reference of project completion during the 12 weeks of coding.


# 🌏 CONTRIBUTIONS 

During this period i have been working on different modules of the project in the three categories:

- **EXISITING FEATURE ENHANCEMENT:** In this category i have been fixing existing bugs in the REST end points and introducing new features on the UI to enhance the user experience.

- **UI EMPROVEMENT:** Introducing new pages to the frontend.

- **BUILDING REST APIS:** The formal backend did not expose all the required APIs to satisfy the UI. I raised more than 12 PRs of new APIs to be consumed by the client.

Let's dive into each category in details to showcase all the contributions with the corresponding screenshots where possible and the respective links to the Pull requests.

##  FEATURE ENHANCEMENT AND BUG FIX  :bug:

I fixed the existing problem that could arise in uploads such as  FILE , VCS or the ULR type. After submitting the file to the backend for-instance the client could also wait up to 10 adjacent calls checking if the ununpack and adj2nest agents has completed their role on the uploaded item so that it can goes on requesting for the creation of the corresponding job of the item.

Sometimes the 10 adjacent calls were not enough for the agents to having completed the work;as the result the corresponding job for the uploaded item could not be created.

My work here was to merge these processes into one in other words through one upload request from the client; i will do the rest of the work on the backend side. Here the client will not need again to wait so that it can continue with the request of the job creation.

![image](https://user-images.githubusercontent.com/66276301/188787353-ad7e5e8e-5cb6-4a6f-979b-92051b031abd.png)
![image](https://user-images.githubusercontent.com/66276301/188787365-df71a36d-6c67-4020-b2d7-e4342aeda004.png)

**Major Pull Requests**

- [fix(API): merge multiple upload-api calls into one.#1](https://github.com/fossology/fossology/pull/2287)
- [fix(MULTIPLE-API-CALLS) merge multiple upload-api calls into one #2](https://github.com/fossology/FOSSologyUI/pull/249)


##  UI EMPROVEMENT (FRONTEND) :sparkles:
 
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

## REST-APIS (BACKEND) :sparkles:

I fixed and created the new REST-APIs on the fossology backend. Some pages on the UI were not integrated due to the absense of the required end-points to be consumed. Others were there but some of them could not work as expected. My work on the backend was to fix and introduce new END-POINTS there. Some of my major modules i focused on to improve were **GROUPS** , **UPLOADS** , **MAINTENANCE** AND **LICENSE**.


### 1. GROUPS

**i. DELETE GROUP API**

I added the delete functionality from the groups module to remove any specific deletable group. This API was required to be consumed by the Delete group page. Through the given **GROUP_ID**__ in the request params, my API can manage the rest of the work.

![image](https://user-images.githubusercontent.com/66276301/188793517-c67f6f36-32a1-49f9-b7a9-1302efb379e1.png)

PR: - [feat(API): delete user group](https://github.com/fossology/fossology/pull/2244)

**ii. GET DELETABLE GROUPS**

I created the end point to return the list of the groups that can be deleted to the calling client. Some groups at fossology are there by default and cannot be deleted. On the delete-group page from the UI needed to know which groups to be listed down which are the ones that are possible to be removed.

![image](https://user-images.githubusercontent.com/66276301/188794792-a8d47911-022b-4021-9086-982bd6b7b434.png)


PR: - [feat(API): list groups that can be deleted](https://github.com/fossology/fossology/pull/2247) 

**iii. GET GROUP MEMBERS WITH THEIR ROLES**

I created the REST-API to return the a list of all group members from a specific group with corresponding roles. This API is integrated on the UI to allow the Admin view all group members from any specific group from the UI.

![image](https://user-images.githubusercontent.com/66276301/188795223-116dc03e-455a-4ef1-9c47-4f95fc817170.png)

PR: - [feat(API): get group members with corresponding roles](https://github.com/fossology/fossology/pull/2251) 

**iv. CHANGE GROUP MEMBER'S PERMISSION**

I created the API for modifying the permission of any member from a particular group. for-instance we want to change a specific member from being an Advisor to an Admin. This API manages that work.

PR: - [feat(API): change group member's permission](https://github.com/fossology/fossology/pull/2259) 

**v. REMOVE MEMBER FROM GROUP**

I created the API to remove a specific user from a particular group. Instead of changing the permission of the user from the group only , we may also need to remove him/her permanently, this functionality is implemented by the API.

![image](https://user-images.githubusercontent.com/66276301/188797257-b4f33e6f-d964-4c10-9089-51ac2a8f9e9d.png)

PR: - [feat(API): remove member from group](https://github.com/fossology/fossology/pull/2269)

**vi. ADD USER TO A GROUP**

I created the API to add the user who is not a part of the group as a member. Once the User is removed from the group, this API makes it possible to add him/her back into the group again.

![image](https://user-images.githubusercontent.com/66276301/188796265-784755eb-c848-486e-8634-1ef98fc41261.png)

PR: - [feat(API): feat(API): add user to a group. ](https://github.com/fossology/fossology/pull/2303)  


### 2. MAINTENANCE

I created the API to initiate the running of the fossology maintenance operations. This is a POST based API which requires the list of options in the request body from the client whose operations are to be run on the backend side.

![image](https://user-images.githubusercontent.com/66276301/188864304-7ef18a93-ceba-4f5a-bea3-3609cb2d0a65.png)

PR: - [feat(API): REST-API to initiate FOSSology maintenance. ](https://github.com/fossology/fossology/pull/2290)  


### 3. LICENSE


**i. IMPORT LICENSE**

I created the REST-API to import the uploaded csv-license file into the backend. The API also returns the appropriate message if the license file was already imported before to handle the existence of duplicates.

![image](https://user-images.githubusercontent.com/66276301/188865187-dda353a5-ee31-49c4-aec9-4e8d6a6521ad.png)

PR: - [feat(API): import csv-license file ](https://github.com/fossology/fossology/pull/2292)  


**ii. REMOVE ADMIN-LICENSE-CANDIDATE API**

I created the API to remove any admin-candidate-license from the database. The API provides more authorization features by allowing only admin to delete a license.

![image](https://user-images.githubusercontent.com/66276301/188866229-5b7f3e97-2061-4067-b339-9df1966237d2.png)

PR: - [feat(API): delete admin-license candidate](https://github.com/fossology/fossology/pull/2298)  

**iii. GET ADMIN-LICENSE CANDIDATES API**

I created the API to give alist of the admin license candidates.

![image](https://user-images.githubusercontent.com/66276301/188867410-93606941-407a-4795-8cd4-be071dff8363.png)

PR: - [feat(API): get admin-license candidates](https://github.com/fossology/fossology/pull/2295)  


## Documentation:📄

During the GSoC period, I got the time to create and organize documentation for both the [**Fossology UI**](https://github.com/fossology/FOSSologyUI) and Fossology [**REST-API**](https://github.com/fossology/fossology). The documentation contains all the user and developer information of the project and is organized in a way to be easily accessible by all.

The weekly documentation of updates can be found at [**FOSSology/gsoc**](https://fossology.github.io/gsoc/docs/2022/ui/updates/samuel/2021-06-24)


<h1 align="center">👨🏻‍🏫 DELIVERABLES <img src="https://api.ezeelo.com/Scripts/QRCode/Done.gif" width="40"></h1>

| Tasks   | Planned | Completed     | Remarks    |
| :---:       |    :----:   |    :---:      |    :---:      |
| Added more than 5 new UI features     | Yes       | :heavy_check_mark: | Added new pages and improved the existing UI. |
| Exposed more than 12 REST APIs  | Yes        | :heavy_check_mark:  | Exposed more APIs on the backend |
| Fix the existing bugs| Yes | :heavy_check_mark: | Fixed some UI issues and improved REST APIs|


## Future enhancements:🚀

- Adding the skeleton loading on the UI components when the items are being fetched.
- Adding search utilities on the select components from the UI.
- Adding the pagination to the GET list APIs where appropriate and it's applicable.
- Completing to add all the remaining pages on the License Administration Section.
- Adding more REST-APIs from the backend.

## Major Takeaways: 📚

- The project has familiarized me to write clean code for the REST-API end points.
- I was taught how to write smart urls for my end points.
- I explored the best practices of writing Javascript codes specifically for React Js.
- Left me with a tangible experience of working remotely.
- Gained the confidence of working on large codebases and learned how to meintain consistency in the enormous community of contributors.
- Furthermore ,I learned the power of collaboration and working in a team.
- Got cool experience on contributing to the opensource projects.
- The last but not least i learned how to code like an expert by refering to the talented engineers a broad.😂

## Links of work done: 🎯

### Pull Requests 🔗

- [Fossology](https://github.com/fossology/fossology/pulls?q=is%3Apr+author%3Adushimsam)
- [FossologyUI](https://github.com/fossology/FOSSologyUI/pulls?q=is%3Apr+author%3Adushimsam)

# Let's get connected!

- [LinkedIn](https://www.linkedin.com/in/samuel-dushimimana-364a19194/)
- [GitHub](https://github.com/dushimsam)
- [Twitter](https://twitter.com/dushsamuel)
 



