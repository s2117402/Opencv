public Mat onCameraFrame(Mat inputFrame) {  
{  
        mRgba = inputFrame;  
        if(mRgba != null){  
               mRgba = inputFrame.rgba();  
                 Mat mRgbaT = mRgba.t();  
                 Core.flip(mRgba.t(), mRgbaT, 0);  
                 Imgproc.resize(mRgbaT, mRgbaT, mRgba.size());  
                 return mRgbaT;  
        }  
        return null;  
 }  

//What I did is define the onCameraFrame method in Interface CameraBridgeViewBase.CvCameraViewListener.
And it will output the picture has been rotated.
