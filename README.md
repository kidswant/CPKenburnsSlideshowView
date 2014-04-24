CPKenburnsSlideshowView
=======================

Use CPKenburnsView

Inspired by Hey Day (photo app)

[Play Movie](http://cl.ly/1P3k0y451L0F)

![sho1](shot1.png)

![shot2](shot2.png)

CPKenburnsSlideshowView use CPKenburnsImage

Required image or imageUrl;

```
@interface CPKenburnsImage : NSObject
@property (nonatomic, strong) UIImage *image;
@property (nonatomic, strong) NSURL *imageUrl;
@property (nonatomic, assign) CGFloat latitude;
@property (nonatomic, assign) CGFloat longitude;
@property (nonatomic, strong) NSString *title;
@property (nonatomic, strong) NSString *subTitle;
@property (nonatomic, strong) NSString *locationDescription;
@property (nonatomic, strong) NSDate *date;
@end
```

```
@protocol CPKenburnsSlideshowViewDeleagte <NSObject>
@optional
- (void)slideshowView:(CPKenburnsSlideshowView *)slideshowView downloadImageUrl:(NSURL *)imageUrl completionBlock:(DownloadCompletionBlock)completionBlock;
- (void)slideshowView:(CPKenburnsSlideshowView *)slideshowView willShowKenBurnsView:(CPKenburnsView *)kenBurnsView;
@end
```

If you use imageUrl,call back
```
- (void)slideshowView:(CPKenburnsSlideshowView *)slideshowView downloadImageUrl:(NSURL *)imageUrl completionBlock:(DownloadCompletionBlock)completionBlock
{
    UIImaage *image = ~~~~;// Download image
    completionBlock(image);
}
```