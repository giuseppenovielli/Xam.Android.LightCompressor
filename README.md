# Xam.Android.LightCompressor

Xamarin.Android Binding library https://github.com/AbedElazizShe/LightCompressor by Giuseppe Novielli

LightCompressor v1.1.1

Documentation Available https://github.com/AbedElazizShe/LightCompressor

# How To use
1.  Add nuget package https://www.nuget.org/packages/Xam.Android.LightCompressor/1.1.1
2.  Copy and paste follow code
3.  Set references to your Xamarin.Android project's

```
var vcl = new VideoCompressorListener();

var configuration = new Configuration(
    VideoQuality.Medium,
    null,
    false,
    1500000, //Bitrate (bit/s)
    false,
    false,
    1280,
    720
  );

var uris = new List<Uri>
      {
          inputUri //=> Source can be provided as content uris
      };

VideoCompressor.Start(context,
                  uris,
                  Android.OS.Environment.DirectoryMovies,
                  vcl,
                  configuration);
                  
public class VideoCompressorListener : Java.Lang.Object, ICompressionListener
{
    public VideoCompressorListener()
    {
    }

    public void OnCancelled(int index)
    {
        System.Diagnostics.Debug.WriteLine("\n\n");
        System.Diagnostics.Debug.WriteLine("OnCancelled");
        System.Diagnostics.Debug.WriteLine(index);

    }

    public void OnFailure(int index, string failureMessage)
    {
        System.Diagnostics.Debug.WriteLine("\n\n");
        System.Diagnostics.Debug.WriteLine("OnFailure");
        System.Diagnostics.Debug.WriteLine(index);
        System.Diagnostics.Debug.WriteLine(failureMessage);
    }

    public void OnProgress(int index, float percent)
    {
        System.Diagnostics.Debug.WriteLine("\n\n");
        System.Diagnostics.Debug.WriteLine("OnProgress");
        System.Diagnostics.Debug.WriteLine(index);
        System.Diagnostics.Debug.WriteLine(percent);
    }

    public void OnStart(int index)
    {
        System.Diagnostics.Debug.WriteLine("\n\n");
        System.Diagnostics.Debug.WriteLine("OnStart");
        System.Diagnostics.Debug.WriteLine(index);
    }

    public async void OnSuccess(int index, long size, string path)
    {
        System.Diagnostics.Debug.WriteLine("\n\n");
        System.Diagnostics.Debug.WriteLine("OnSuccess");
        System.Diagnostics.Debug.WriteLine(index);
        System.Diagnostics.Debug.WriteLine(size);
        System.Diagnostics.Debug.WriteLine(path);

    }
}                  
```                  
                  
