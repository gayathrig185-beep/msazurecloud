import pulumi
from pulumi_azure_native import storage as az_storage

# Rules: globally unique, 3-24 characters, lowercase letters and digits only.
# Example: "stlabamit001"
STORAGE_ACCOUNT_NAME = "stlabgayathri001"


def create_storage(rg, account_name=STORAGE_ACCOUNT_NAME):
    env = pulumi.get_stack()

    # ---- Part A goes here ----
    account = az_storage.StorageAccount(
        "sa",
        resource_group_name=rg.name,
        account_name=account_name,
        location=rg.location,
        sku=az_storage.SkuArgs(name=az_storage.SkuName.STANDARD_LRS),
        kind=az_storage.Kind.STORAGE_V2,
        allow_blob_public_access=False,
        enable_https_traffic_only=True,
        minimum_tls_version=az_storage.MinimumTlsVersion.TLS1_2,
        tags={"environment": env, "managed-by": "pulumi"},
    )

    pulumi.export("storage_account", account.name)
    pulumi.export("blob_endpoint", account.primary_endpoints.apply(lambda e: e.blob))

    # ---- Part B goes here ----
    container = az_storage.BlobContainer(
        "data",
        resource_group_name=rg.name,
        account_name=account.name,
        container_name="data",
        public_access=az_storage.PublicAccess.NONE,
    )
    # ---- Part C goes here ---- 
    az_storage.Blob(
        "hello",
        resource_group_name=rg.name,
        account_name=account.name,
        container_name=container.name,
        blob_name="hello.txt",
        type=az_storage.BlobType.BLOCK,
        source=pulumi.StringAsset("Hello from Pulumi!"),
    )   
    return account
