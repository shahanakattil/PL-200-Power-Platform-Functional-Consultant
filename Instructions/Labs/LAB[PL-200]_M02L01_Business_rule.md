# Practice Lab 2.1 – Business rules

## Scenario

You are a Power Platform functional consultant and have been assigned to the Fabrikam project for the next stage of the project.

In this practice lab, you will be creating business rules to show and hide the lookup columns in the model-driven app form for the Resource table and to set the status of Milestone rows to completed when the percentage complete is 100%.

## Lab objectives
In this lab, you will perform:

+ Task 1: Create Resource business rules
+ Task 2: Create Milestone business rules
  
## Exercise 1 – Create business rules

### Task 1.1 – Create Resource business rules

1. Navigate to the Power Apps Maker portal `https://make.powerapps.com`

1. Make sure you are in your **Development** environment.

    ![](../media/ex1(1).png)

1. Select **Solutions**.

1. Open the **Fabrikam Environmental** solution.

1. In the **Objects**(1) pane on the left, expand **Tables**(2).

1. Select the **Resource**(3) table.

1. Under **Customizations**(4), select **Business rules**(5).

    ![](../media/mod-02;lab-01(1).png)

1. Select the existing business rule, **Set Resource Name**, to open the business rule designer. Analyze how this business rule works. This business rule controls the visibility and requirement for the resource name based on the selection of resource type.

1. **Close** the Business rule designer.

1. Select **Done**.

1. Select **+ New business rule** from the command bar.

    ![](../media/mod-02;lab-01(2).png)

1. In the Business rule designer, next to the **New business rule** name at the top of the screen, select the drop-down caret.

1. Enter `Resource Type Internal` for **Business rule name**. You can select on the drop-down caret again to collapse this section.

    ![](../media/mod-02;lab-01(3).png)

1. In the **Scope** drop-down in the top-right of the Business rules designer, select **All Forms**.

    ![](../media/mod-02;lab-01(4).png)

1. Select the **Condition** tile(1) in the canvas and in the **Properties**(2) pane enter `Check Resource Type`(3) for **Display Name**. 

1. In the **Rules** section, select **Resource Type**(4) for **Field**, select **Equals**(5) for **Operator**, select **Value**(6) for **Type**, and select **Internal** for **Value**.

1. Select **Apply**(7).

    ![](../media/mod-02;lab-01(5).png)

1. Select the **Components** tab.

1. Drag the **Set Visibility** action and place it on the **True** side (on the right-hand side) of the condition.

1. Enter `Show User`(1) for **Display Name**.

1. In the **Visibility** section, select **User**(2) and **Yes**(3).

1. Select **Apply**(4).

    ![](../media/mod-02;lab-01(6).png)

1. Drag another **Set Visibility** action from the **Components** tab and place it on the right-hand side of the **Show User** tile.

1. Enter `Hide Contact`(1) for **Display Name**. In the **Visibility** section, select **Contact**(2) and **No**(3).

1. Select **Apply**(4).

    ![](../media/mod-02;lab-01(7).png)

1. Select **+ Add** and select **Add Set Business Required** and then select the plus icon to the right of the **Hide Contact** tile.

    ![](../media/mod-02;lab-01(8).png)

1. Enter `User Required`(1) for **Display Name**. In the **Business Required** section, select **User**(2) and **Business Required**(3).

1. Select **Apply**(4).

    ![](../media/mod-02;lab-01(9).png)

1. Select **+ Add** and select **Add Set Business Required** and then select the plus icon to the right of the **User Required** tile.

1. Enter `Contact Not Required`(1) for **Display Name**. In the **Business Required** section, select **Contact**(2) and **Not Business Required**(3). Select **Apply**(4).

    ![](../media/mod-02;lab-01(10).png)

1. The **Business Rule (Text View)** should read as follows:

    ```
    IF
     Resource Type equals "Internal"
    THEN
     Show field User
     Hide field Contact
     Set User as Business Required
     Set Contact as Not Business Required
    ```

1. Select **Save**. You should see the message Validation successful.

    ![](../media/mod-02;lab-01(11).png)

1. Select **Activate**.

    ![](../media/mod-02;lab-01(12).png)

1. In the **Process Activate Confirmation** dialog, select **Activate**.

1. Select **Save As**.

1. Next to **New business rule** name at the top of the screen, select the drop-down caret.

1. Enter `Resource Type External` for **Business rule name**. Collapse the top section.

1. Select the **Check Resource Type** tile.

1. In the **Rules** section, uncheck **Internal** and check **External**(1).

1. Select **Apply**(2).

    ![](../media/mod-02;lab-01(13).png)

1. Select the **Show User** tile.

1. Enter `Hide User` for **Display Name**. Select **User**, **No** in the **Visibility** section and select **Apply**.

    ![](../media/mod-02;lab-01(14).png)

1. Select the **Hide Contact** tile.

1. Enter `Show Contact` for **Display Name**. Select **Contact**, **Yes** in the **Visibility** section and select **Apply**.

    ![](../media/mod-02;lab-01(15).png)

1. Select the **User Required** tile.

1. Enter `User Not Required` for **Display Name**, select **Not Business Required** in the **Business Required** section and select **Apply**.

    ![](../media/mod-02;lab-01(16).png)

1. Select the **Contact Not Required** tile.

1. Enter `Contact Required` for **Display Name**, select **Business Required** for **Status** and select **Apply**.

    ![](../media/mod-02;lab-01(17).png)

1. The **Business Rule (Text View)** should read as follows:

    ```
    IF
     Resource Type equals "External"
    THEN
     Hide field User
     Show field Contact
     Set User as Not Business Required
     Set Contact as Business Required
    ```

    ![](../media/mod-02;lab-01(18).png)

1. Select **Save**. You should see the message that Validation was successful.

1. Select **Activate**.

1. In the **Process Activate Confirmation** dialog, select **Activate**.

1. Close the business rule designer tab.

1. Select **Done**.
   
   > **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - Click the (...) icon located at the upper right corner of the lab guide section and navigate to the Lab Validation Page.
> - Hit the Validate button for the corresponding task.If you receive a success message, you can proceed to the next task. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.


### Task 1.2 – Create Milestone business rules

1. In the **Objects** pane on the left, select the **Milestone** table.

1. Under **Customizations**, select **Business rules**.

    ![](../media/mod-02;lab-01(19).png)

1. Select **+ New business rule**.

1. Next to **New business rule** name at the top of the screen, select the drop-down caret.

1. Enter `Milestone Completed`(1) for **Business rule name**. Collapse the top section.

1. In the **Scope** drop-down in the top-right of the business rules designer, select **Entity**(2).

    ![](../media/mod-02;lab-01(20).png)

1. Select the **Condition** tile in the canvas and in the **Properties** pane, enter `Percentage Complete` for **Display Name**.

1. In the **Rules** section, select **Milestone Percentage Complete** for **Field**, select **Equals** for **Operator**, select **Value** for **Type**, and enter `100` for **Value**.

    ![](../media/mod-02;lab-01(22).png)

1. At the top of the **Rules** section, select **+ New** to add **Rule 2**.

1. In the **Rule 2** section, select **Milestone status** for **Field**, select **Does not equal** for **Operator**, select **Value** for **Type**, and check **Completed** and **Cancelled** for **Value**.

1. Select **AND** for **Rule Logic**.

1. Select **Apply**.

    ![](../media/mod-02;lab-01(23).png)

1. The **Condition Expression (Text View)** should read as follows:

    ```
    (Milestone Percentage Complete Equals [100]) AND (Milestone status Does not equal [Completed,Cancelled])
    ```

1. Select **+ Add** and select **Add Set Field Value** and then select the plus icon to the right of the **Condition** tile.

1. Enter `Mark Complete` for **Display Name**. In the **Field Value** section, select **Milestone status** for **Field**, select **Value** for **Type**, and select **Completed** for **Value**.

1. Select **Apply**.

    ![](../media/mod-02;lab-01(26).png)

1. The **Business Rule (Text View)** should read as follows:

    ```
    IF
     Milestone Percentage Complete equals 100 AND Milestone status does not equal "Completed,Cancelled"
    THEN
     Set Milestone status to "Completed"
    ```

1. Select **Save**. You should see the message that Validation was successful.

1. Select **Activate**.

1. In the **Process Activate Confirmation** dialog, select **Activate**.

1. Close the business rule designer tab.

1. Select **Done**.


## Challenge (Optional)

Edit the **Set Resource Name** business rule on the **Resource** table to hide both lookup columns if resource type is not selected and set as not business required.

### Review
In this lab, you created resource and milestone business rules
