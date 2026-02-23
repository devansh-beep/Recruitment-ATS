**JOB RECRUITMENT & HIRING MANAGEMENT SYSTEM**

**NAME: **

**Phase 4 Report: Process Automation (Admin)**

-   **Validation Rules**:

    -   We created one key validation rule on the **Application\_\_c**
        object. This rule prevents a user from saving a new application
        if the related **Candidate\_\_c** record\'s **Resume\_\_c**
        field is blank, ensuring that all applications have a resume
        before proceeding.

> ![](/mnt/data/media/media/image1.png){width="5.708272090988626in"
> height="1.3065912073490813in"}
>
> ![](/mnt/data/media/media/image2.png){width="5.72638779527559in"
> height="1.5822747156605423in"}

-   **Approval Process**:

    -   We implemented a formal, multi-step **Approval Process** on the
        **Job\_\_c** object. The process automatically triggers when a
        new job is created with a status of \"Pending Approval.\" It
        locks the record and assigns an approval request to the user
        listed in the **Hiring_Manager\_\_c** field, ensuring proper
        sign-off before a job becomes active.

```{=html}
<!-- -->
```
-   **Flow Builder**:

    -   We utilized a **Record-Triggered Flow**. This flow was
        configured to run whenever an **Application\_\_c** record is
        updated to have a **Status\_\_c** of \"Interview.\" Upon
        triggering, the flow automatically creates a new, related
        **Interview\_\_c** record, streamlining the transition between
        hiring stages. We did not build any Screen Flows, Scheduled
        Flows, or other Auto-launched Flows in this project.

> ![](/mnt/data/media/media/image3.png){width="6.571502624671916in"
> height="0.13105096237970254in"}
>
> ![](/mnt/data/media/media/image4.png){width="5.948561898512686in"
> height="2.7198884514435697in"}

-   **Email Alerts**:

    -   We implemented email alerts using **Batch Apex** in Phase 5,
        rather than using the declarative Email Alert action. Our batch
        job was configured to send a follow-up email to candidates whose
        applications were still in progress.

```{=html}
<!-- -->
```
-   **Field Updates**:

    -   We used **Field Update** actions as part of our **Approval
        Process**. When a Job\_\_c record was approved, a field update
        changed its Status\_\_c field to \"Approved.\" Similarly, when
        it was rejected, a field update changed the status to
        \"Rejected.\"

> ![](/mnt/data/media/media/image5.png){width="6.010533683289589in"
> height="0.512752624671916in"}
>
> ![](/mnt/data/media/media/image6.png){width="5.978816710411198in"
> height="1.6838188976377952in"}
>
> ![](/mnt/data/media/media/image7.png){width="5.582066929133858in"
> height="1.8448151793525809in"}
>
> ![](/mnt/data/media/media/image8.png){width="5.6503313648293965in"
> height="2.196655730533683in"}
>
> ![](/mnt/data/media/media/image9.png){width="5.695939413823272in"
> height="2.723650481189851in"}
