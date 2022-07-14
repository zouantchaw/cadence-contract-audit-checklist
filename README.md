### Access Control
Is something `pub`(public) when it should be `access`(contract)
### Resource Interfaces
Is something exposed in a public interface when it shouldn't be?
### AuthAccount
Is the `AuthAccount` ever passed into the contract? If so, immediate red flag.
### Metadata Views
### Admin Resource
Is the `create Admin` function stored inside of the Admin resource?
If so, it allows bad actors with that resource to copy infinite copies of the resource.
