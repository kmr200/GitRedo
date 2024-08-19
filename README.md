#### Step 1:
````zsh
git checkout git_1
touch firstFile.txt
````
<img width="379" alt="SCR-20240819-umzk" src="https://github.com/user-attachments/assets/1c299ecf-8563-4ff1-976e-ddce800eec0a">

````zsh
git add firstFile.txt
git commit -m "New file: firstFile.txt"
````
#### Step 2:
````zsh
touch secondFile.txt
````
<img width="394" alt="SCR-20240819-unzs" src="https://github.com/user-attachments/assets/296ec9aa-0d46-4350-9610-351a2005cfcf">

````zsh
git add secondFile.txt
git commit -m "New fiel: secondFile.txt"
````

#### Step 3:
````zsh
git checkout git_2
git merge git_1
````
<img width="341" alt="SCR-20240819-upkf" src="https://github.com/user-attachments/assets/087c9f3b-52ab-430d-b314-dc4459fbbd5e">

#### Step 4:
<img width="399" alt="SCR-20240819-uqac" src="https://github.com/user-attachments/assets/9174cfe3-419c-4441-9bca-ba49c17fc2f7">

````zsh
git commit -a -m "Modified secondFile"
````
#### Step 5:
<img width="402" alt="SCR-20240819-uqvb" src="https://github.com/user-attachments/assets/01f9a75c-2f3e-4df9-b613-50c822a91020">

````zsh
git commit -a -m "Edited secondFile"
````
#### Step 6:
````zsh
git merge git_2 --no-ff
````
<img width="476" alt="SCR-20240820-baej" src="https://github.com/user-attachments/assets/e5a40315-7be1-41e3-96c9-02f016ab2333">

<img width="403" alt="SCR-20240820-balb" src="https://github.com/user-attachments/assets/fb0d36d3-a583-47ba-b235-881a1199aa40">

After resolving the conflict and leaving all 4 lines:

<img width="397" alt="SCR-20240820-bavc" src="https://github.com/user-attachments/assets/18aa753a-18fc-4e51-adad-aece8fd14581">

````zsh
git commit -a -m "Resolved conflict"
````
<img width="476" alt="SCR-20240820-bbix" src="https://github.com/user-attachments/assets/417afb35-fc98-469c-b66f-89cf42bae00f">

#### Step 7:
<img width="386" alt="SCR-20240820-bbyr" src="https://github.com/user-attachments/assets/dd89b893-dfb6-4b93-a9b3-be7c1db81782">

````zsh
git commit -a -m "Modified firstFile"
````
#### Step 8:
<img width="393" alt="SCR-20240820-bclz" src="https://github.com/user-attachments/assets/ec2e3030-1e90-4ebb-b710-afb8106a3334">

````zsh
git commit -a -m "Edited firstFile"
````
#### Step 9:
Taking the hash of the commit to be transfered:
````zsh
git log
````
<img width="491" alt="SCR-20240820-bhhw" src="https://github.com/user-attachments/assets/14339d9d-fad4-4ebc-9dda-27b8e4c8229e">

Then we create the patch file:

<img width="467" alt="SCR-20240820-bikz" src="https://github.com/user-attachments/assets/e51e69b8-c564-484b-a520-27babf046c4d">

Then we apply it in git_2:

````zsh
git checkout git_2
git am 0001-Modified-firstFile.patch
````

Results:

<img width="466" alt="SCR-20240820-biyr" src="https://github.com/user-attachments/assets/cc93a7e0-de45-478c-8963-80c654b2595b">

#### Step 10:
First we need the hash of the commit:

<img width="480" alt="SCR-20240820-bjdf" src="https://github.com/user-attachments/assets/a921201a-cf97-44de-8de1-795bd2c68a21">

Then we apply it in git_2:

<img width="609" alt="SCR-20240820-bjpc" src="https://github.com/user-attachments/assets/c810355f-faaf-4ac9-a15d-6cb8e7fc7c25">

#### Step 11:

For this purpose we will move HEAD pointer up by 2 commits using command:
````zsh
git reset --soft "HEAD^^"
````
Soft mode ensures that all the changes remain.
And then we make a new commit:
```` zsh
git commit -a -m "Concatinating the last two commits"
````

Result:

![SCR-20240820-blrt](https://github.com/user-attachments/assets/fd83681b-0313-4510-9a2a-b77f821d4120)

#### Step 12:

We will use git commit --amend command:

![SCR-20240820-bmok](https://github.com/user-attachments/assets/cd616a88-7af7-464c-9239-30db0c478757)

#### Step 13:

<img width="478" alt="SCR-20240820-bndv" src="https://github.com/user-attachments/assets/5fdb4608-8c2b-4b8c-805c-ea5c1a28cf70">

#### Step 14:

<img width="505" alt="SCR-20240820-bnnf" src="https://github.com/user-attachments/assets/3fe3a281-001b-4480-8b33-0dc7088d99dd">

#### Step 15:

````zsh
git reset --hard HEAD^^
````

<img width="445" alt="SCR-20240820-bnxc" src="https://github.com/user-attachments/assets/23dd5223-2344-4256-9d36-bc53b29ea3f5">

#### Step 16:

<img width="482" alt="SCR-20240820-bogz" src="https://github.com/user-attachments/assets/58e6898b-e3de-431a-8af0-0528c75673c4">

#### Step 17:

<img width="569" alt="SCR-20240820-boug" src="https://github.com/user-attachments/assets/42375b17-ad91-420e-b654-4ddc875887d8">

#### Step 18:

Edited firstFile from folder2:

<img width="386" alt="SCR-20240820-bpec" src="https://github.com/user-attachments/assets/7d98902d-e2b7-40c9-8896-ca87d9b48852">
<img width="458" alt="SCR-20240820-bqni" src="https://github.com/user-attachments/assets/37df3d92-d6f1-438e-8018-84c7b948768c">

#### Step 19:

Edited firstFile from folder1:

<img width="395" alt="SCR-20240820-bpvb" src="https://github.com/user-attachments/assets/5c61665b-e95f-4555-923c-e79e1226c663">

Prepare for Step 20:

````zsh
git stash
````

#### Step 20:

![SCR-20240820-bsdn](https://github.com/user-attachments/assets/144b20c1-280c-4523-8cb4-27da0f6f35b0)

````zsh
git pull origin git_1
````

This is how firstFile looks now:

<img width="389" alt="SCR-20240820-bunr" src="https://github.com/user-attachments/assets/ac99cafd-d67c-4b9a-aa00-b27987c3044b">

Pushing:

<img width="450" alt="SCR-20240820-buvl" src="https://github.com/user-attachments/assets/3e28ccc8-ce17-4781-a262-2d4d5afaa66b">

Conflict while stashing:

<img width="512" alt="SCR-20240820-bwct" src="https://github.com/user-attachments/assets/1956f406-cdc6-4bcb-9e4c-3a758b0cdb71">

Handling conflicts:

<img width="388" alt="SCR-20240820-bwjw" src="https://github.com/user-attachments/assets/7969c4fd-4e81-42f3-85fd-8900a95c8b44">

I'm going to leave only the stashed changes:

<img width="375" alt="SCR-20240820-bwpl" src="https://github.com/user-attachments/assets/244dcd5b-df85-4e71-8f19-df37a2238be1">

Result:

<img width="701" alt="SCR-20240820-bxoi" src="https://github.com/user-attachments/assets/5d19a0f7-5737-403a-b650-131acd7beacb">
