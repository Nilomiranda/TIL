
In your LiveView in the `mount` function do some of the following

- assign to a variable a relation of uploaded files or file you have
	- `uploaded_files` with initial value of `[]` if handling multiple files
	- `uploaded_file` wtith the initial value of `nil` if handling single file
- use `allow_upload` to allow an upload to a given name
	- it accepts `name` as second param (`socket` is the first passed by the pipe `|>` operator)
	- `accept` is the param that will dictate file formats accepted in this specific upload
	- `max_entries` number of files allowed for this upload

```ex
def mount(_params, _session, socket) do
	{
		:ok,
		socket
			|> assign(:uploaded_file, nil) # if single file
			|> assign(:uploaded_files, []) # if multi files
			|> allow_upload(:profile_pic, accept: ~w(.png .svg .jpeg), max_entries: 1) # use 2 or more if multi upload 
	}
end
```

This will make `uploads` available in the `socket.assigns`. (e.g.: `socket.assigns.uploads`)

> Note: If using a your main `live_view` markup file renders other components, don't forget to pass `@uploads` to this component as a property.

```html
<div>
	<.live_component module={UserProfile} uploads={@uploads} />
</div>
```


You'll then make usage of `live_file_input` component to handle this uploaded "allowed" in your live view.

```html
<.live_file_input upload={@uploads.profile_pic} />
```

The portion `@uploads.profile_pic` where `profile_pic` is the argument you passed for the `name` param of `allow_upload`, in this case `profile_pic`