# Oe-Workflow-Inbox
oe-workflow-inbox component helps to list all the tasks assigned to a particular user based on the username or roles.

Based on the current session all the tasks are fetched and listed according to the following types :
Total : All the tasks assigned to the user/roles
Role : All the tasks assigned to the roles
Pending : All the pending tasks for that user/role
Completed : All completed tasks for that user/role

## Search
User can search a particular task based on its name.

## Refresh
Fetches the updated list of tasks.

## Task Action
Clicking on a pending task launches a custom form associated with the task.
oe-workflow-modeler can be used to associate a polymer form to the user  task.
User task contains a formKey which takes the custom element's name/import path(if import path is given, it will be imported by oe-workflow-inbox)
This custom form can use oe-workflow-form-behavior to complete the current task.

## oe-workflow-form-behavior
It contains the following properties :
taskInfo : It contains model data.
_task : It contains the entire task object.

It contains the following methods :
makeAjaxCall : It can be used to perform server calls.
completeTask : It accepts a payload, id and a callback function.The payload data should be handled by the form as it varies from task to task.

## Usage
Follow the below steps to setup oe-workflow-inbox:
1)Add oe-workflow-inbox as a bower dependency to your application.

2)Add a new UI Route to access the tasks.
example :
{
                type : elem
                name : oe-workflow-inbox
                path : /my-tasks
                import : bower_components/oe-workflow-inbox/oe-workflow-inbox.html
}
3)Add a Navigation Link.
Example :
{
                name : My tasks
                label : My tasks
                url : /my-tasks
                group : root
}
4)Open oe-studio and goto workflow-modeler
                Open the required workflow(e.g. Loan application present in CASSI Bank)
                Select user task, goto the forms tab in the right panel and enter the element name or import path in formKey.
                Save with a new name and version then save and publish.
5)Goto model designer
                Open the model to which workflow is to be attached(e.g. LoanApplication) in grid view.
                Select options goto attach workflow-inbox
                Select oe-worklfow
                Add the new workflow created above with a process name(e.g.LoanApplicationNew)

