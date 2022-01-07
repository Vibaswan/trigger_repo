# Trigger_Repo
this repository is a supporting repository for the [Github action introduction](https://github.com/Vibaswan/Gihub_Actions_introduction)
we will be only focusing on repository dispatch

## Repository dispatch

```yml
- name: Repository Dispatch
  uses: peter-evans/repository-dispatch@v1
  with:
   token: ${{ secrets.ACCESS_TOKEN }}
   repository: Vibaswan/Gihub_Actions_and_pyTest
   event-type: triggered-from-changes
```

we use the github action `peter-evans/repository-dispatch@v1` and we have to specify which repo we are targeting i.e. `Vibaswan/Gihub_Actions_and_pyTest`
please note that `token` is a necessity and we have it here as a secret
