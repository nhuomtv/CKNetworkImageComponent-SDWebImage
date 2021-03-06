# CKNetworkImageComponent-SDWebImage
Implement image downloader for CKNetworkImageComponent (ComponentKit) with SDWebImage.

### Usage:

Declare image downloader as property.

```ruby
@interface IAWTimelineContext ()
…
@property (strong, nonatomic, readwrite) IAWCKImageDownloader *imageDownloader;
…
@end
```

Create and assign image downloader for context:
```ruby
+ (instancetype)context {
	…

	itemContext.imageDownloader = [IAWCKImageDownloader sharedManager];
	
	…
}
```
And create network image component with image downloader.
```ruby
CKComponent *avatarComponent = [CKNetworkImageComponent newWithURL:avatarURL
	                                                   imageDownloader:context.imageDownloader
	                                                         scenePath:nil
	                                                              size:{ AVATAR_SIZE, AVATAR_SIZE }
	                                                           options:options
	                                                        attributes:attributes];
```
