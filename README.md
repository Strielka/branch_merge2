1. На локальном репозитории сделать ветки для:
- Postman
- Jmeter
- CheckLists
- Bag Reports
- SQL
- Charles
- Mobile testing

	git clone https://github.com/Strielka/branch_merge2.git
	cd branch_merge2 
	git branch Postman
	...
	git branch Bag_Reports 
	...

2. Запушить все ветки на внешний репозиторий
	git push -u origin branch_merge2 Postman Jmeter CheckLists Bag_Reports SQL Charles Mobile_testing
		or 
	git push origin --all

3. В ветке Bag Reports сделать текстовый документ со структурой баг репорта
	git checkout Bag_Reports
	vim br1.txt
	In the 'POST  /users /' is not registered with the phone number

		Description:
		It’s not possible to sign up with a phone number In the 'POST  /users /' 

		Steps to reproduce:
		 Pre-register with phone number ( POST exist, POST verification)

		Sign up with this phone number (POST users)

		Actual result:
		{"user": "Temporary user does not exits or not approved"} 
		Status 404 (Not found)

		Expected result:
		Registration of user data by phone number is completed successfully

4. Запушить структуру багрепорта на внешний репозиторий
	git add br1 && git commit -m "add bug report"
	git push

5. Вмержить ветку Bag Reports в Main
	git checkout main
	git merge Bag_Reports

6. Запушить main на внешний репозиторий.
	git push origin main

7. В ветке CheckLists набросать структуру чек листа.
	git checkout CheckLists
	vim checklist_lays.txt

8. Запушить структуру на внешний репозиторий
	git add checklist_lays.txt && git commit -m "add checklist of chips"
	git push

9. На внешнем репозитории сделать Pull Request ветки CheckLists в main
	Compare & pull request -> comment: modified with checklist -> Create pull request -> Merge pull request -> Confirm merge
    
10. Синхронизировать Внешнюю и Локальную ветки Main
	git checkout main
