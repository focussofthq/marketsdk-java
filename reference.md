# Reference
## Marketplace
<details><summary><code>client.marketplace.getMarketplace() -> MarketplaceObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Settings are changed in the dashboard, separately for test and live.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.marketplace().getMarketplace();
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Sellers
<details><summary><code>client.sellers.listSellers() -> SellerList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.sellers().listSellers(
    ListSellersRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `Optional<Double>` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `Optional<String>` — The `next_cursor` of the previous page.
    
</dd>
</dl>

<dl>
<dd>

**externalId:** `Optional<String>` — Find the seller with this external id.
    
</dd>
</dl>

<dl>
<dd>

**status:** `Optional<ListSellersRequestStatus>` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.sellers.createSeller(request) -> SellerObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.sellers().createSeller(
    CreatePartyDto
        .builder()
        .externalId("external_id")
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `CreatePartyDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.sellers.getSeller(id) -> SellerObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.sellers().getSeller(
    "id",
    GetSellerRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.sellers.eraseSeller(id) -> SellerObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Removes the name, external id, metadata, storefront, and review text, and takes the listings down. Orders and reputation stay, without personal data.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.sellers().eraseSeller(
    "id",
    EraseSellerRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.sellers.updateSeller(id, request) -> SellerObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.sellers().updateSeller(
    "id",
    UpdateSellerRequest
        .builder()
        .body(
            UpdatePartyDto
                .builder()
                .build()
        )
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>

<dl>
<dd>

**request:** `UpdatePartyDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.sellers.putStorefront(id, request) -> StorefrontObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.sellers().putStorefront(
    "id",
    StorefrontDto
        .builder()
        .name("name")
        .slug("jane-templates")
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>

<dl>
<dd>

**name:** `String` 
    
</dd>
</dl>

<dl>
<dd>

**slug:** `String` — Lowercase letters, digits, and hyphens. Unique per marketplace.
    
</dd>
</dl>

<dl>
<dd>

**description:** `Optional<String>` 
    
</dd>
</dl>

<dl>
<dd>

**metadata:** `Optional<Map<String, String>>` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.sellers.createOnboardingLink(id, request) -> OnboardingLinkObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

The first link creates the seller's connected account on your Stripe account: Express, with Stripe collecting what the law requires, your platform paying Stripe's fees and bearing losses, and only transfers requested. Send the seller to the link; their payouts status follows as Stripe reports it.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.sellers().createOnboardingLink(
    "id",
    OnboardingLinkDto
        .builder()
        .returnUrl("return_url")
        .refreshUrl("refresh_url")
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>

<dl>
<dd>

**returnUrl:** `String` — Where Stripe sends the seller when they finish or leave onboarding.
    
</dd>
</dl>

<dl>
<dd>

**refreshUrl:** `String` — Where Stripe sends the seller if the link expired. Create a new link there.
    
</dd>
</dl>

<dl>
<dd>

**country:** `Optional<String>` — The seller's country, two letters. Used only when the seller's Stripe account is created, on the first link. Defaults to your Stripe account's country.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.sellers.getSellerProfile(id) -> SellerProfileObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Callable with a publishable key. Shows only what a buyer may see.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.sellers().getSellerProfile(
    "id",
    GetSellerProfileRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Buyers
<details><summary><code>client.buyers.listBuyers() -> BuyerList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.buyers().listBuyers(
    ListBuyersRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `Optional<Double>` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `Optional<String>` — The `next_cursor` of the previous page.
    
</dd>
</dl>

<dl>
<dd>

**externalId:** `Optional<String>` — Find the buyer with this external id.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.buyers.createBuyer(request) -> BuyerObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.buyers().createBuyer(
    CreatePartyDto
        .builder()
        .externalId("external_id")
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `CreatePartyDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.buyers.getBuyer(id) -> BuyerObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.buyers().getBuyer(
    "id",
    GetBuyerRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.buyers.eraseBuyer(id) -> BuyerObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.buyers().eraseBuyer(
    "id",
    EraseBuyerRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.buyers.updateBuyer(id, request) -> BuyerObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.buyers().updateBuyer(
    "id",
    UpdateBuyerRequest
        .builder()
        .body(
            UpdatePartyDto
                .builder()
                .build()
        )
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>

<dl>
<dd>

**request:** `UpdatePartyDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Categories
<details><summary><code>client.categories.listCategories() -> CategoryList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.categories().listCategories(
    ListCategoriesRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `Optional<Double>` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `Optional<String>` — The `next_cursor` of the previous page.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.categories.createCategory(request) -> CategoryObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.categories().createCategory(
    CreateCategoryDto
        .builder()
        .key("ui-kits")
        .name("name")
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**key:** `String` — Your key for the category. Unique per marketplace.
    
</dd>
</dl>

<dl>
<dd>

**name:** `String` 
    
</dd>
</dl>

<dl>
<dd>

**description:** `Optional<String>` 
    
</dd>
</dl>

<dl>
<dd>

**parent:** `Optional<String>` — Another category of this marketplace.
    
</dd>
</dl>

<dl>
<dd>

**attributeSchema:** `Optional<AttributeSchemaObject>` 
    
</dd>
</dl>

<dl>
<dd>

**fee:** `Optional<CategoryFeeDto>` — Overrides the marketplace's platform fee for listings in this category. Null uses the marketplace fee.
    
</dd>
</dl>

<dl>
<dd>

**prohibited:** `Optional<Boolean>` — Listings in a prohibited category cannot be published (section 9.4).
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.categories.getCategory(id) -> CategoryObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.categories().getCategory(
    "id",
    GetCategoryRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.categories.updateCategory(id, request) -> CategoryObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.categories().updateCategory(
    "id",
    UpdateCategoryDto
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>

<dl>
<dd>

**name:** `Optional<String>` 
    
</dd>
</dl>

<dl>
<dd>

**description:** `Optional<String>` 
    
</dd>
</dl>

<dl>
<dd>

**parent:** `Optional<String>` 
    
</dd>
</dl>

<dl>
<dd>

**fee:** `Optional<CategoryFeeDto>` 
    
</dd>
</dl>

<dl>
<dd>

**prohibited:** `Optional<Boolean>` — Listings in a prohibited category cannot be published. Listings already published stay until moderated.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.categories.getAttributeSchema(id) -> AttributeSchemaObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.categories().getAttributeSchema(
    "id",
    GetAttributeSchemaRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.categories.putAttributeSchema(id, request) -> AttributeSchemaObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Refused if a listing already in the category would no longer fit.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.categories().putAttributeSchema(
    "id",
    PutAttributeSchemaRequest
        .builder()
        .body(
            AttributeSchemaObject
                .builder()
                .attributes(
                    Arrays.asList(
                        AttributeDefinitionObject
                            .builder()
                            .key("format")
                            .type(AttributeDefinitionObjectType.STRING)
                            .build()
                    )
                )
                .build()
        )
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>

<dl>
<dd>

**request:** `AttributeSchemaObject` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Listings
<details><summary><code>client.listings.listListings() -> ListingList</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

With a publishable key, only published listings are listed.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.listings().listListings(
    ListListingsRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `Optional<Double>` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `Optional<String>` — The `next_cursor` of the previous page.
    
</dd>
</dl>

<dl>
<dd>

**seller:** `Optional<String>` 
    
</dd>
</dl>

<dl>
<dd>

**category:** `Optional<String>` 
    
</dd>
</dl>

<dl>
<dd>

**status:** `Optional<ListListingsRequestStatus>` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.listings.createListing(request) -> ListingObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.listings().createListing(
    CreateListingDto
        .builder()
        .seller("sel_034XtPDs7UJ0TXzTsdaHZa")
        .title("title")
        .price(
            MoneyDto
                .builder()
                .amount(4900.0)
                .currency("USD")
                .build()
        )
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `CreateListingDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.listings.createListings(request) -> BulkListingsObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.listings().createListings(
    BulkCreateListingsDto
        .builder()
        .listings(
            Arrays.asList(
                CreateListingDto
                    .builder()
                    .seller("sel_034XtPDs7UJ0TXzTsdaHZa")
                    .title("title")
                    .price(
                        MoneyDto
                            .builder()
                            .amount(4900.0)
                            .currency("USD")
                            .build()
                    )
                    .build()
            )
        )
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**listings:** `List<CreateListingDto>` — All are created, or none.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.listings.getListing(id) -> ListingObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

With a publishable key, only a published listing can be retrieved.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.listings().getListing(
    "id",
    GetListingRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.listings.updateListing(id, request) -> ListingObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.listings().updateListing(
    "id",
    UpdateListingDto
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>

<dl>
<dd>

**category:** `Optional<String>` 
    
</dd>
</dl>

<dl>
<dd>

**title:** `Optional<String>` 
    
</dd>
</dl>

<dl>
<dd>

**description:** `Optional<String>` 
    
</dd>
</dl>

<dl>
<dd>

**price:** `Optional<MoneyDto>` 
    
</dd>
</dl>

<dl>
<dd>

**quantity:** `Optional<Double>` — The total. Cannot go below what open orders have reserved.
    
</dd>
</dl>

<dl>
<dd>

**attributes:** `Optional<Map<String, Object>>` 
    
</dd>
</dl>

<dl>
<dd>

**metadata:** `Optional<Map<String, String>>` 
    
</dd>
</dl>

<dl>
<dd>

**expiresAt:** `Optional<OffsetDateTime>` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.listings.publishListing(id) -> ListingObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Needs an active seller, verified when seller verification is on, and a category that is not prohibited.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.listings().publishListing(
    "id",
    PublishListingRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.listings.unpublishListing(id) -> ListingObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.listings().unpublishListing(
    "id",
    UnpublishListingRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.listings.removeListing(id, request) -> ListingObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.listings().removeListing(
    "id",
    RemoveListingDto
        .builder()
        .reason("reason")
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>

<dl>
<dd>

**reason:** `String` — Recorded with the removal.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.listings.listMedia(id) -> MediaList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.listings().listMedia(
    "id",
    ListMediaRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.listings.createMedia(id, request) -> MediaUploadObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a signed URL, valid for 10 minutes. PUT the file there, then complete the upload. The file is stored under a path that begins with the marketplace id.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.listings().createMedia(
    "id",
    CreateMediaDto
        .builder()
        .contentType(CreateMediaDtoContentType.IMAGE_JPEG)
        .sizeBytes(1.1)
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>

<dl>
<dd>

**contentType:** `CreateMediaDtoContentType` 
    
</dd>
</dl>

<dl>
<dd>

**sizeBytes:** `Double` — The exact size of the file, in bytes. At most 10 MB.
    
</dd>
</dl>

<dl>
<dd>

**position:** `Optional<Double>` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.listings.completeMedia(id) -> MediaObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Checks the stored file against the declared type and size.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.listings().completeMedia(
    "id",
    CompleteMediaRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.listings.deleteMedia(id) -> MediaObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.listings().deleteMedia(
    "id",
    DeleteMediaRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Search
<details><summary><code>client.search.searchListings() -> ListingList</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Full text over title and description, with filters and sorting. Only published listings with something available are returned. Callable with a publishable key.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.search().searchListings(
    SearchListingsRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**q:** `Optional<String>` — Full text over title and description.
    
</dd>
</dl>

<dl>
<dd>

**category:** `Optional<String>` 
    
</dd>
</dl>

<dl>
<dd>

**seller:** `Optional<String>` 
    
</dd>
</dl>

<dl>
<dd>

**minPrice:** `Optional<Double>` — Minor units.
    
</dd>
</dl>

<dl>
<dd>

**maxPrice:** `Optional<Double>` — Minor units.
    
</dd>
</dl>

<dl>
<dd>

**attributes:** `Optional<Map<String, Object>>` — Attribute filters, as attributes[key]=value for equality, or attributes[key][gte]=n and attributes[key][lte]=n for numbers. Numeric filters need a category.
    
</dd>
</dl>

<dl>
<dd>

**sort:** `Optional<SearchListingsSearchRequestSort>` — Relevance needs q. Default newest.
    
</dd>
</dl>

<dl>
<dd>

**limit:** `Optional<Double>` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `Optional<String>` — The next_cursor of the previous page.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Orders
<details><summary><code>client.orders.listOrders() -> OrderList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.orders().listOrders(
    ListOrdersRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `Optional<Double>` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `Optional<String>` — The `next_cursor` of the previous page.
    
</dd>
</dl>

<dl>
<dd>

**buyer:** `Optional<String>` 
    
</dd>
</dl>

<dl>
<dd>

**seller:** `Optional<String>` 
    
</dd>
</dl>

<dl>
<dd>

**listing:** `Optional<String>` 
    
</dd>
</dl>

<dl>
<dd>

**state:** `Optional<ListOrdersRequestState>` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.orders.createOrder(request) -> OrderObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

The buyer commits to buy. Quantity is reserved at once. With payments off the order is committed; with payments on it awaits payment.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.orders().createOrder(
    CreateOrderDto
        .builder()
        .listing("lst_034XtPDs7UJ0TXzTsdaHZa")
        .buyer("buy_034XtPDs7UJ0TXzTsdaHZa")
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**listing:** `String` 
    
</dd>
</dl>

<dl>
<dd>

**buyer:** `String` — The buyer placing the order. The actor for this transition.
    
</dd>
</dl>

<dl>
<dd>

**quantity:** `Optional<Double>` 
    
</dd>
</dl>

<dl>
<dd>

**checkout:** `Optional<CheckoutUrlsDto>` — Payments on only. With these, the order's payment includes a Stripe-hosted checkout URL; without them, a client secret for Stripe Elements on your own page.
    
</dd>
</dl>

<dl>
<dd>

**metadata:** `Optional<Map<String, String>>` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.orders.getOrder(id) -> OrderObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.orders().getOrder(
    "id",
    GetOrderRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.orders.listOrderEvents(id) -> OrderEventList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.orders().listOrderEvents(
    "id",
    ListOrderEventsRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.orders.claimOrder(id, request) -> OrderObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Called from your server. `actor` says which end user is acting; we check they are a party to the order and may make this transition.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.orders().claimOrder(
    "id",
    ClaimOrderRequest
        .builder()
        .body(
            ActorDto
                .builder()
                .actor("buy_034XtPDs7UJ0TXzTsdaHZa")
                .build()
        )
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>

<dl>
<dd>

**request:** `ActorDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.orders.confirmOrder(id, request) -> OrderObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Called from your server. `actor` says which end user is acting; we check they are a party to the order and may make this transition.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.orders().confirmOrder(
    "id",
    ConfirmOrderRequest
        .builder()
        .body(
            ActorDto
                .builder()
                .actor("buy_034XtPDs7UJ0TXzTsdaHZa")
                .build()
        )
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>

<dl>
<dd>

**request:** `ActorDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.orders.backOutOfOrder(id, request) -> OrderObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Called from your server. `actor` says which end user is acting; we check they are a party to the order and may make this transition. Writes a backed_out reputation event against the actor.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.orders().backOutOfOrder(
    "id",
    BackOutOfOrderRequest
        .builder()
        .body(
            ActorDto
                .builder()
                .actor("buy_034XtPDs7UJ0TXzTsdaHZa")
                .build()
        )
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>

<dl>
<dd>

**request:** `ActorDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.orders.proposeCancel(id, request) -> OrderObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Called from your server. `actor` says which end user is acting; we check they are a party to the order and may make this transition. The other party can accept within the agreement window. A declined or lapsed proposal changes nothing.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.orders().proposeCancel(
    "id",
    ProposeCancelRequest
        .builder()
        .body(
            ActorDto
                .builder()
                .actor("buy_034XtPDs7UJ0TXzTsdaHZa")
                .build()
        )
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>

<dl>
<dd>

**request:** `ActorDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.orders.acceptCancel(id, request) -> OrderObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Called from your server. `actor` says which end user is acting; we check they are a party to the order and may make this transition.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.orders().acceptCancel(
    "id",
    AcceptCancelRequest
        .builder()
        .body(
            ActorDto
                .builder()
                .actor("buy_034XtPDs7UJ0TXzTsdaHZa")
                .build()
        )
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>

<dl>
<dd>

**request:** `ActorDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.orders.declineCancel(id, request) -> OrderObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Called from your server. `actor` says which end user is acting; we check they are a party to the order and may make this transition.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.orders().declineCancel(
    "id",
    DeclineCancelRequest
        .builder()
        .body(
            ActorDto
                .builder()
                .actor("buy_034XtPDs7UJ0TXzTsdaHZa")
                .build()
        )
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>

<dl>
<dd>

**request:** `ActorDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.orders.listOrderReviews(id) -> ReviewList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.orders().listOrderReviews(
    "id",
    ListOrderReviewsRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.orders.createReview(id, request) -> ReviewObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Called from your server. `actor` says which end user is acting; we check they are a party to the order and may make this transition. Only on a completed order, inside the review window, once per party. Hidden until both have reviewed or the window closes.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.orders().createReview(
    "id",
    CreateReviewDto
        .builder()
        .actor("buy_034XtPDs7UJ0TXzTsdaHZa")
        .rating(1.1)
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>

<dl>
<dd>

**actor:** `String` — The buyer id or seller id of the end user doing this. We check they are a party to the order and may make this transition.
    
</dd>
</dl>

<dl>
<dd>

**rating:** `Double` 
    
</dd>
</dl>

<dl>
<dd>

**body:** `Optional<String>` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Reviews
<details><summary><code>client.reviews.listReviews() -> ReviewList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.reviews().listReviews(
    ListReviewsRequest
        .builder()
        .subject("subject")
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `Optional<Double>` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `Optional<String>` — The `next_cursor` of the previous page.
    
</dd>
</dl>

<dl>
<dd>

**subject:** `String` — The buyer or seller the reviews are about.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.reviews.getReview(id) -> ReviewObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.reviews().getReview(
    "id",
    GetReviewRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Reputation
<details><summary><code>client.reputation.listReputationEvents() -> ReputationEventList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.reputation().listReputationEvents(
    ListReputationEventsRequest
        .builder()
        .party("party")
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `Optional<Double>` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `Optional<String>` — The `next_cursor` of the previous page.
    
</dd>
</dl>

<dl>
<dd>

**party:** `String` — The buyer or seller whose events to list.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.reputation.voidReputationEvent(id, request) -> ReputationEventObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

For the customer's team. Writes a second event pointing at the first. The voided event stops counting. Nothing is deleted.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.reputation().voidReputationEvent(
    "id",
    VoidDto
        .builder()
        .reason("reason")
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>

<dl>
<dd>

**reason:** `String` — Why the event is voided. Recorded on the voiding event.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Payments
<details><summary><code>client.payments.listPayments() -> PaymentList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.payments().listPayments(
    ListPaymentsRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `Optional<Double>` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `Optional<String>` — The `next_cursor` of the previous page.
    
</dd>
</dl>

<dl>
<dd>

**order:** `Optional<String>` — Only the payment for this order.
    
</dd>
</dl>

<dl>
<dd>

**status:** `Optional<ListPaymentsRequestStatus>` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.payments.getPayment(id) -> PaymentObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.payments().getPayment(
    "id",
    GetPaymentRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.payments.updatePayment(id, request) -> PaymentObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.payments().updatePayment(
    "id",
    UpdatePaymentRequest
        .builder()
        .body(
            UpdateMetadataDto
                .builder()
                .metadata(
                    new HashMap<String, String>() {{
                        put("key", "value");
                    }}
                )
                .build()
        )
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>

<dl>
<dd>

**request:** `UpdateMetadataDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.payments.retryPaymentRelease(id) -> PaymentObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

For a release that failed, for example because the seller could not yet receive transfers. A release is also tried again by itself when the seller becomes able to receive payouts.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.payments().retryPaymentRelease(
    "id",
    RetryPaymentReleaseRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.payments.listRefunds() -> RefundList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.payments().listRefunds(
    ListRefundsRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `Optional<Double>` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `Optional<String>` — The `next_cursor` of the previous page.
    
</dd>
</dl>

<dl>
<dd>

**payment:** `Optional<String>` 
    
</dd>
</dl>

<dl>
<dd>

**order:** `Optional<String>` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.payments.createRefund(request) -> RefundObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Recorded at once with status `pending`, then made at Stripe. If the seller's share was already released, the transfer is reversed in the same proportion, so your fee is given back in proportion too.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.payments().createRefund(
    CreateRefundDto
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**payment:** `Optional<String>` — The payment to refund. Give this or `order`.
    
</dd>
</dl>

<dl>
<dd>

**order:** `Optional<String>` — The order whose payment to refund. Give this or `payment`.
    
</dd>
</dl>

<dl>
<dd>

**amount:** `Optional<Double>` — Minor units. Defaults to everything not yet refunded.
    
</dd>
</dl>

<dl>
<dd>

**reason:** `Optional<CreateRefundDtoReason>` 
    
</dd>
</dl>

<dl>
<dd>

**metadata:** `Optional<Map<String, String>>` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.payments.getRefund(id) -> RefundObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.payments().getRefund(
    "id",
    GetRefundRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.payments.updateRefund(id, request) -> RefundObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.payments().updateRefund(
    "id",
    UpdateRefundRequest
        .builder()
        .body(
            UpdateMetadataDto
                .builder()
                .metadata(
                    new HashMap<String, String>() {{
                        put("key", "value");
                    }}
                )
                .build()
        )
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>

<dl>
<dd>

**request:** `UpdateMetadataDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Trust
<details><summary><code>client.trust.createVerification(id, request) -> VerificationObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a Stripe Identity session on your Stripe account and returns its page, once. Only the outcome and the session id are kept; no document image or document data. When seller verification is on, a seller can publish only once verified.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.trust().createVerification(
    "id",
    CreateVerificationDto
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>

<dl>
<dd>

**returnUrl:** `Optional<String>` — Where Stripe sends the seller after the verification page.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.trust.listVerifications() -> VerificationList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.trust().listVerifications(
    ListVerificationsRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `Optional<Double>` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `Optional<String>` — The `next_cursor` of the previous page.
    
</dd>
</dl>

<dl>
<dd>

**seller:** `Optional<String>` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.trust.getVerification(id) -> VerificationObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.trust().getVerification(
    "id",
    GetVerificationRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.trust.cancelVerification(id) -> VerificationObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.trust().cancelVerification(
    "id",
    CancelVerificationRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.trust.listDisputes() -> DisputeList</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Filter by `stage` for a queue.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.trust().listDisputes(
    ListDisputesRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `Optional<Double>` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `Optional<String>` — The `next_cursor` of the previous page.
    
</dd>
</dl>

<dl>
<dd>

**stage:** `Optional<ListDisputesRequestStage>` 
    
</dd>
</dl>

<dl>
<dd>

**order:** `Optional<String>` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.trust.getDispute(id) -> DisputeObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.trust().getDispute(
    "id",
    GetDisputeRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.trust.listDisputeEvidence(id) -> DisputeEvidenceList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.trust().listDisputeEvidence(
    "id",
    ListDisputeEvidenceRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.trust.addDisputeEvidence(id, request) -> DisputeEvidenceObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Only while the dispute is in its evidence stage.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.trust().addDisputeEvidence(
    "id",
    AddEvidenceDto
        .builder()
        .actor("actor")
        .body("body")
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>

<dl>
<dd>

**actor:** `String` — The buyer or seller giving evidence.
    
</dd>
</dl>

<dl>
<dd>

**body:** `String` 
    
</dd>
</dl>

<dl>
<dd>

**links:** `Optional<List<String>>` — Links to files the party provided, such as photos you store. HTTPS only.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.trust.closeDisputeEvidence(id) -> DisputeObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.trust().closeDisputeEvidence(
    "id",
    CloseDisputeEvidenceRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.trust.decideDispute(id, request) -> DisputeObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Your team's decision: who it went against, in writing, and with payments on, how much goes back to the buyer. On a claimed order, deciding against the party who disputed upholds the claim and completes the order; deciding against the claimant cancels it.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.trust().decideDispute(
    "id",
    DecideDisputeDto
        .builder()
        .against(DecideDisputeDtoAgainst.BUYER)
        .note("note")
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>

<dl>
<dd>

**against:** `DecideDisputeDtoAgainst` — Who the decision went against. They get a dispute_lost reputation event; the other party gets dispute_won.
    
</dd>
</dl>

<dl>
<dd>

**note:** `String` — The written decision, kept with the dispute.
    
</dd>
</dl>

<dl>
<dd>

**refundAmount:** `Optional<Double>` — Payments on only. Minor units to refund to the buyer; the rest goes to the seller. Defaults: a claimed order whose claim is upheld refunds nothing; one whose claim is rejected refunds everything; a dispute on a completed order refunds nothing.
    
</dd>
</dl>

<dl>
<dd>

**decidedBy:** `Optional<String>` — Who on your team decided, for the record. Up to 200 characters.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.trust.openDispute(id, request) -> DisputeObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

On a claimed order, by the party who did not claim: the order becomes disputed. On a completed order, by either party inside the dispute window: the order stays completed.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.trust().openDispute(
    "id",
    OpenDisputeDto
        .builder()
        .actor("buy_034XtPDs7UJ0TXzTsdaHZa")
        .reason("reason")
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>

<dl>
<dd>

**actor:** `String` — The buyer or seller opening the dispute.
    
</dd>
</dl>

<dl>
<dd>

**reason:** `String` — What went wrong, in their words.
    
</dd>
</dl>

<dl>
<dd>

**metadata:** `Optional<Map<String, String>>` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Moderation
<details><summary><code>client.moderation.listFlags() -> FlagList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.moderation().listFlags(
    ListFlagsRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `Optional<Double>` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `Optional<String>` — The `next_cursor` of the previous page.
    
</dd>
</dl>

<dl>
<dd>

**status:** `Optional<ListFlagsRequestStatus>` 
    
</dd>
</dl>

<dl>
<dd>

**target:** `Optional<String>` — Only flags on this listing, seller, or review.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.moderation.createFlag(request) -> FlagObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

On behalf of the end user who reported it.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.moderation().createFlag(
    CreateFlagDto
        .builder()
        .target("lst_034XtPDs7UJ0TXzTsdaHZa")
        .reporter("buy_034XtPDs7UJ0TXzTsdaHZa")
        .reason(CreateFlagDtoReason.PROHIBITED_ITEM)
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**target:** `String` — A listing, seller, or review id.
    
</dd>
</dl>

<dl>
<dd>

**reporter:** `String` — The end user reporting it: a buyer id or a seller id.
    
</dd>
</dl>

<dl>
<dd>

**reason:** `CreateFlagDtoReason` 
    
</dd>
</dl>

<dl>
<dd>

**note:** `Optional<String>` — The reporter's own words.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.moderation.getFlag(id) -> FlagObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.moderation().getFlag(
    "id",
    GetFlagRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.moderation.getModerationQueue() -> ModerationQueueObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.moderation().getModerationQueue(
    GetModerationQueueRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**targetType:** `Optional<GetModerationQueueRequestTargetType>` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.moderation.listModerationActions() -> ModerationActionList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.moderation().listModerationActions(
    ListModerationActionsRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `Optional<Double>` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `Optional<String>` — The `next_cursor` of the previous page.
    
</dd>
</dl>

<dl>
<dd>

**target:** `Optional<String>` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.moderation.createModerationAction(request) -> ModerationActionObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Resolves the target's open flags and logs who acted and why.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.moderation().createModerationAction(
    CreateModerationActionDto
        .builder()
        .target("target")
        .action(CreateModerationActionDtoAction.DISMISS)
        .reason("reason")
        .actor("actor")
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**target:** `String` — The listing, seller, or review acted on.
    
</dd>
</dl>

<dl>
<dd>

**action:** `CreateModerationActionDtoAction` — `dismiss` closes the open flags and changes nothing else. `remove_content` removes a listing or a review; a removed review stops counting toward reputation. `suspend_seller` suspends the seller, or the seller of a listing, or a seller who wrote a review: they cannot publish or take orders, and their listings leave search. `reinstate_seller` lifts a suspension.
    
</dd>
</dl>

<dl>
<dd>

**reason:** `String` — Why. Kept with the action.
    
</dd>
</dl>

<dl>
<dd>

**actor:** `String` — Who on your team took the action, for the log.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Webhooks
<details><summary><code>client.webhooks.listWebhookEndpoints() -> WebhookEndpointList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.webhooks().listWebhookEndpoints(
    ListWebhookEndpointsRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `Optional<Double>` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `Optional<String>` — The `next_cursor` of the previous page.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.webhooks.createWebhookEndpoint(request) -> WebhookEndpointObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the signing secret, once. Every delivery carries `MarketSDK-Signature: t=<time>,v1=<HMAC-SHA256 of "<time>.<body>">`.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.webhooks().createWebhookEndpoint(
    CreateWebhookEndpointDto
        .builder()
        .url("https://shop.example/marketsdk/webhooks")
        .enabledEvents(
            Arrays.asList(CreateWebhookEndpointDtoEnabledEventsItem.ALL)
        )
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**url:** `String` — An HTTPS URL on the public internet.
    
</dd>
</dl>

<dl>
<dd>

**enabledEvents:** `List<CreateWebhookEndpointDtoEnabledEventsItem>` — Event types to send, or `*` for all.
    
</dd>
</dl>

<dl>
<dd>

**description:** `Optional<String>` 
    
</dd>
</dl>

<dl>
<dd>

**metadata:** `Optional<Map<String, String>>` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.webhooks.getWebhookEndpoint(id) -> WebhookEndpointObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.webhooks().getWebhookEndpoint(
    "id",
    GetWebhookEndpointRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.webhooks.deleteWebhookEndpoint(id) -> DeletedWebhookEndpointObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.webhooks().deleteWebhookEndpoint(
    "id",
    DeleteWebhookEndpointRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.webhooks.updateWebhookEndpoint(id, request) -> WebhookEndpointObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.webhooks().updateWebhookEndpoint(
    "id",
    UpdateWebhookEndpointDto
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>

<dl>
<dd>

**url:** `Optional<String>` 
    
</dd>
</dl>

<dl>
<dd>

**enabledEvents:** `Optional<List<UpdateWebhookEndpointDtoEnabledEventsItem>>` 
    
</dd>
</dl>

<dl>
<dd>

**description:** `Optional<String>` 
    
</dd>
</dl>

<dl>
<dd>

**status:** `Optional<UpdateWebhookEndpointDtoStatus>` — Turn the endpoint off, or back on after it was turned off.
    
</dd>
</dl>

<dl>
<dd>

**metadata:** `Optional<Map<String, String>>` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.webhooks.rotateWebhookSecret(id) -> WebhookEndpointObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the new secret, once. The old one stops at once.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.webhooks().rotateWebhookSecret(
    "id",
    RotateWebhookSecretRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.webhooks.listWebhookDeliveries() -> WebhookDeliveryList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.webhooks().listWebhookDeliveries(
    ListWebhookDeliveriesRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `Optional<Double>` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `Optional<String>` — The `next_cursor` of the previous page.
    
</dd>
</dl>

<dl>
<dd>

**endpoint:** `Optional<String>` 
    
</dd>
</dl>

<dl>
<dd>

**status:** `Optional<ListWebhookDeliveriesRequestStatus>` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.webhooks.getWebhookDelivery(id) -> WebhookDeliveryObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.webhooks().getWebhookDelivery(
    "id",
    GetWebhookDeliveryRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.webhooks.replayWebhookDelivery(id) -> WebhookDeliveryObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new delivery of the same event to the same endpoint.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.webhooks().replayWebhookDelivery(
    "id",
    ReplayWebhookDeliveryRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.webhooks.listEvents() -> EventList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.webhooks().listEvents(
    ListEventsRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `Optional<Double>` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `Optional<String>` — The `next_cursor` of the previous page.
    
</dd>
</dl>

<dl>
<dd>

**type:** `Optional<ListEventsRequestType>` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.webhooks.getEvent(id) -> EventObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```java
client.webhooks().getEvent(
    "id",
    GetEventRequest
        .builder()
        .build()
);
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `String` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

