# Cadence Contract Audit Checklist

  Dev-friendly checklist that you can use when auditing cadence contracts. Submit a pull request to add to the list. - **Builders build**

### Access Control
  - [ ] Is something `pub` when it should be `access`(contract)?
  - [ ] something `pub(set)` when it should not be?

### Resource Interfaces
 - [ ] Is something exposed in a public interface when it shouldn't be?(ex. exposing `Withdraw` function in `CollectionPublic` resource interface)

### AuthAccount
 - [ ] Is the `AuthAccount` ever passed into the contract? If so, immediate red flag.

### Metadata Views
 - [ ] Is `MetadataViews.ResolverCollection` implemented so that you can expose that interface later?
 - [ ] Is `ResolverCollection` exposed to the public path?
 - [ ] If the NFT is going to be traded for purpose, is `providerPath` implemented so people can link `Collection.Provider`
 - [ ] If the NFT has an 'edition', is it implemented in the `MetadataViews`
 - [ ] Is there a way to view the metadata of the NFT without having to call the `borrowEntireNFT` func? If not, use `MetadataViews`

### Admin Resource
 - [ ] Is the `create Admin` function stored inside of the Admin resource? If so, it allows bad actors with that resource to copy infinite copies of the resource.
 - [ ] Is access to the `Admin` resource given through a capability receiver? If not, do so!
 
### Storage Slots

 - [ ] Are you linking to a generic path? Is so, DON'T!
 - [ ] Are you using generic names for contracts? If so, DON'T!

### Linking
 - [ ] Are you linking to a generic path? If so, DON'T!
 - [ ] Are you using generic names for contracts? If so, DON'T!

### Naming Conventions
