---
swagger: "2.0"
x-collection-name: Google Cloud Billing
x-complete: 0
info:
  title: Google Cloud Billing API Update Billing Information
  description: |-
    Sets or updates the billing account associated with a project. You specify
    the new billing account by setting the `billing_account_name` in the
    `ProjectBillingInfo` resource to the resource name of a billing account.
    Associating a project with an open billing account enables billing on the
    project and allows charges for resource usage. If the project already had a
    billing account, this method changes the billing account used for resource
    usage charges.

    *Note:* Incurred charges that have not yet been reported in the transaction
    history of the Google Cloud Console may be billed to the new billing
    account, even if the charge occurred before the new billing account was
    assigned to the project.

    The current authenticated user must have ownership privileges for both the
    [project](https://cloud.google.com/docs/permissions-overview#h.bgs0oxofvnoo
    ) and the [billing
    account](https://support.google.com/cloud/answer/4430947).

    You can disable billing on the project by setting the
    `billing_account_name` field to empty. This action disassociates the
    current billing account from the project. Any billable activity of your
    in-use services will stop, and your application could stop functioning as
    expected. Any unbilled charges to date will be billed to the previously
    associated account. The current authenticated user must be either an owner
    of the project or an owner of the billing account for the project.

    Note that associating a project with a *closed* billing account will have
    much the same effect as disabling billing on the project: any paid
    resources used by the project will be shut down. Thus, unless you wish to
    disable billing, you should always call this method with the name of an
    *open* billing account.
  contact:
    name: Google
    url: https://google.com
  version: v1
host: cloudbilling.googleapis.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /v1/{name}/billingInfo:
    get:
      summary: Get Billing Information
      description: |-
        Gets the billing information for a project. The current authenticated user
        must have [permission to view the
        project](https://cloud.google.com/docs/permissions-overview#h.bgs0oxofvnoo
        ).
      operationId: cloudbilling.projects.getBillingInfo
      x-api-path-slug: v1namebillinginfo-get
      parameters:
      - in: path
        name: name
        description: The resource name of the project for which billing information
          isretrieved
      responses:
        200:
          description: OK
      tags:
      - Billing
    put:
      summary: Update Billing Information
      description: |-
        Sets or updates the billing account associated with a project. You specify
        the new billing account by setting the `billing_account_name` in the
        `ProjectBillingInfo` resource to the resource name of a billing account.
        Associating a project with an open billing account enables billing on the
        project and allows charges for resource usage. If the project already had a
        billing account, this method changes the billing account used for resource
        usage charges.

        *Note:* Incurred charges that have not yet been reported in the transaction
        history of the Google Cloud Console may be billed to the new billing
        account, even if the charge occurred before the new billing account was
        assigned to the project.

        The current authenticated user must have ownership privileges for both the
        [project](https://cloud.google.com/docs/permissions-overview#h.bgs0oxofvnoo
        ) and the [billing
        account](https://support.google.com/cloud/answer/4430947).

        You can disable billing on the project by setting the
        `billing_account_name` field to empty. This action disassociates the
        current billing account from the project. Any billable activity of your
        in-use services will stop, and your application could stop functioning as
        expected. Any unbilled charges to date will be billed to the previously
        associated account. The current authenticated user must be either an owner
        of the project or an owner of the billing account for the project.

        Note that associating a project with a *closed* billing account will have
        much the same effect as disabling billing on the project: any paid
        resources used by the project will be shut down. Thus, unless you wish to
        disable billing, you should always call this method with the name of an
        *open* billing account.
      operationId: cloudbilling.projects.updateBillingInfo
      x-api-path-slug: v1namebillinginfo-put
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: name
        description: The resource name of the project associated with the billing
          informationthat you want to update
      responses:
        200:
          description: OK
      tags:
      - Billing
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---