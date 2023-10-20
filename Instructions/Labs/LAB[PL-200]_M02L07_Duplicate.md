# Module 2 : Lab 2.7 - Duplicate detection

## Scenario

You are a Power Platform functional consultant and have been assigned to the Fabrikam project for the next stage of the project.

In this practice lab, you will implement duplicate detection rules so that duplicate projects cannot be created for the same program.

## Lab objectives
In this lab, you will perform:

+ Task 1: Create duplicate detection rule
  
## Exercise 1 – Create new duplicate detection rule

In this exercise, you will create a new duplicate detection rule that will mark a Project as duplicate if it has the same project title and program.

### Task 1.1 – Create duplicate detection rule

1. Navigate to the Power Platform admin center <https://admin.powerplatform.microsoft.com>.

1. Select **Environments** from the left navigation pane.

1. Select the **Development** environment.

1. Select **Settings**.

1. Expand **Data management**.

1. Select **Duplicate detection rules**.

    ![](../media/mod-02;lab-07(1).png)

1. Select **New**.

1. Enter `Duplicate project`(1) for **Name**.

1. Select **Project** for both **Base Record Type**(2) and **Matching Record Type**(3).

    ![](../media/Mod-02;lab-07(2).png)

1. Check the **Exclude inactive matching records**(1) box.

1. Under **Field**, select **Project Title**(2).

1. Select **Exact Match** for **Criteria**(2).

1. Check the **Ignore Blank Values** box(2).

    ![](../media/Mod-02;lab-07(3).png)

1. Add another field, select **Program**.

1. Select **Exact Match** for **Criteria**.

1. Check the **Ignore Blank Values** box.

    ![](../media/mod-02;lab-07(4).png)

1. Select **Save**.

1. Select **Publish**.

1. Select **OK**.

1. Select **Close**.

### Review
In this lab, you created new duplicate detection rule.
